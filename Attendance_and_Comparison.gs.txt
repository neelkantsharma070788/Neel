/**
 * Attendance & Team Comparison — add-on server functions.
 *
 * Keep this as a SEPARATE .gs file in the SAME Apps Script project as your
 * existing Code.gs. Apps Script shares one global scope across all .gs files,
 * so these functions reuse the helpers already defined in Code.gs
 * (CONFIG, TEAM_ORDER, ensureWorkbookReady_, getCurrentUserAccess_,
 * assertTeamAccess_, canViewTeam_, canViewAgent_, getAgents_, getWorkbook_,
 * getHeaderMap_, normalizeDate_, getCanonicalAgentName_, isLeadAgentName_,
 * countWeekdays_, getMonthlyUtilization, getKraDashboard).
 *
 * The enhanced Index.html calls:
 *   google.script.run.getAttendance({ team, month })
 *   google.script.run.getTeamComparison({ month })
 */

/**
 * Returns, for a team + month, which dates each (non-lead, viewable) agent
 * has a daily entry with production. The client builds the calendar heatmap.
 *
 * @param {{team:string, month:string}} request  month is "yyyy-MM".
 * @return {{team:string, month:string, workingDays:number,
 *           agents:string[], presentByAgent:Object<string,string[]>}}
 */
function getAttendance(request) {
  ensureWorkbookReady_();
  const month = request && request.month
    ? String(request.month)
    : Utilities.formatDate(new Date(), Session.getScriptTimeZone(), "yyyy-MM");
  const team = request && request.team ? request.team : TEAM_ORDER[0];

  const access = getCurrentUserAccess_();
  assertTeamAccess_(team, access);

  const monthStart = new Date(`${month}-01T00:00:00`);
  const monthEnd = new Date(monthStart);
  monthEnd.setMonth(monthEnd.getMonth() + 1);

  const agents = getAgents_(team)
    .filter((agent) => !isLeadAgentName_(agent))
    .filter((agent) => canViewAgent_(access, team, agent));
  const agentSet = {};
  agents.forEach((agent) => { agentSet[agent] = true; });

  const sheet = getWorkbook_().getSheetByName(CONFIG.sheets.entries);
  const headerMap = getHeaderMap_(sheet);
  const rows = sheet.getLastRow() > 1
    ? sheet.getRange(2, 1, sheet.getLastRow() - 1, sheet.getLastColumn()).getValues()
    : [];

  const presentByAgent = {};
  agents.forEach((agent) => { presentByAgent[agent] = {}; });

  rows.forEach((row) => {
    const rowTeam = String(row[headerMap.Team] || "").trim();
    if (rowTeam !== team) return;
    const workDate = normalizeDate_(row[headerMap["Work Date"]]);
    if (!workDate || workDate < monthStart || workDate >= monthEnd) return;
    const agent = getCanonicalAgentName_(rowTeam, String(row[headerMap.Agent] || "").trim());
    if (!agentSet[agent]) return;
    const totalVolume = Number(row[headerMap["Total Volume"]]) || 0;
    const productiveHours = Number(row[headerMap["Productive Hours"]]) || 0;
    if (totalVolume <= 0 && productiveHours <= 0) return;
    const key = Utilities.formatDate(workDate, Session.getScriptTimeZone(), "yyyy-MM-dd");
    presentByAgent[agent][key] = true;
  });

  const result = {};
  agents.forEach((agent) => {
    result[agent] = Object.keys(presentByAgent[agent]).sort();
  });

  return {
    team,
    month,
    workingDays: countWeekdays_(monthStart, monthEnd),
    agents,
    presentByAgent: result,
  };
}

/**
 * Returns per-team KPI summaries for every team the current user can view.
 * Reuses getMonthlyUtilization (utilization KPIs) and getKraDashboard
 * (KRA rating / target-met) so the numbers match the rest of the portal.
 *
 * @param {{month:string}} request  month is "yyyy-MM".
 * @return {{month:string, teams:Object[]}}
 */
function getTeamComparison(request) {
  ensureWorkbookReady_();
  const month = request && request.month
    ? String(request.month)
    : Utilities.formatDate(new Date(), Session.getScriptTimeZone(), "yyyy-MM");
  const access = getCurrentUserAccess_();

  const teams = TEAM_ORDER.filter((team) => canViewTeam_(access, team));
  const summaries = teams.map((team) => {
    const util = getMonthlyUtilization({ month, team });
    const kra = getKraDashboard({ month, team });
    return {
      team,
      totalVolume: util.totalVolume,
      productiveHours: util.productiveHours,
      avgUtilization: util.avgUtilization,
      activeAgents: util.activeAgents,
      avgRating: kra.avgRating,
      targetMet: kra.targetMet,
      kraActiveAgents: kra.activeAgents,
      targetMetPct: kra.activeAgents ? kra.targetMet / kra.activeAgents : 0,
    };
  });

  return { month, teams: summaries };
}
