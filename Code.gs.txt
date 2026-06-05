const SHEET_NAME = "JGW - Check By Phone May 2026 Onwards";
// Optional but recommended: paste the spreadsheet ID from the master sheet URL here.
// Example URL: https://docs.google.com/spreadsheets/d/SPREADSHEET_ID/edit
const SPREADSHEET_ID = "";
const SPREADSHEET_FILE_NAME = "JGW - Check By Phone May 2026 Onwards";
const MONTHLY_FOLLOWUP_ARCHIVE_PREFIX = "JGW - Check By Phone";
const MONTHLY_FOLLOWUP_ARCHIVE_SHEET_NAME = "Follow-ups";
const MONTHLY_FOLLOWUP_ARCHIVE_TRIGGER = "monthlyFollowupArchiveTrigger";
const LEGACY_IMPORT_SHEET_NAME = "Old Master Import";
// Optional: paste the separate 85,000-row client reference spreadsheet ID here.
// Keep this blank if the Client Reference Data tab is inside the same master spreadsheet.
const CLIENT_REFERENCE_SPREADSHEET_ID = "1wiSN6Eipnc3rQm3c_N2TyLa_WoxacjeJ4x38I_ukM5I";
const CLIENT_REFERENCE_SHEET_NAME = "Client Reference Data";
const CLIENT_REFERENCE_INDEX_SHEET_NAME = "Client Reference Index";
const AGENT_ASSIGNMENT_SHEET_NAME = "CRM Agent Assignments";
const OLD_MASTER_SPREADSHEET_ID = "";
const OLD_MASTER_SHEET_NAME = "";
const SYNC_LOCK_WAIT_MS = 30000;
const CRM_SYNC_ATTEMPT_LOG_ENABLED = false;
const CRM_PRESENCE_PROPERTY_KEY = "CRM_ACTIVE_USERS_JSON";
const CRM_PRESENCE_ACTIVE_MS = 5 * 60 * 1000;
const BULK_OUTCOME_COMPLETED = "Bulk Payments Setup Successfully";
const BULK_OUTCOME_AWAITING = "Awaiting Creditor Response";
const CRM_SYNC_ERROR_EMAILS = [
  "neelkant.sharma@prth.com",
  "atish.mukherjee@prth.com",
  "varun.dogra@prth.com",
  "sachin.s@prth.com",
  "ansh.saxena@prth.com"
];
const CRM_ADMIN_USERS = [
  "neelkant.sharma@prth.com",
  "varun.dogra@prth.com"
];
const ALLOWED_CRM_USERS = [
  "neelkant.sharma@prth.com",
  "rohit.chandel@prth.com",
  "sachin.s@prth.com",
  "ansh.saxena@prth.com",
  "naman.negi@prth.com",
  "rahul.sharma3@prth.com",
  "ruhani.garg@prth.com",
  "narinder.singh1@prth.com",
  "rahul.dhiman1@prth.com",
  "vikram.tanwar@prth.com",
  "nitin.mehra@prth.com",
  "amit.rana@prth.com",
  "simran.s@prth.com",
  "varun.dogra@prth.com",
  "shomik.dasgupta@prth.com",
  "atish.mukherjee@prth.com"
];
const CRM_USER_NAMES = {
  "neelkant.sharma@prth.com": "Neel Sharma",
  "rohit.chandel@prth.com": "Rohit Chandel",
  "sachin.s@prth.com": "Sachin Sharma",
  "ansh.saxena@prth.com": "Ansh Saxena",
  "naman.negi@prth.com": "Naman Singh Negi",
  "rahul.sharma3@prth.com": "Rahul Sharma",
  "ruhani.garg@prth.com": "Ruhani Garg",
  "narinder.singh1@prth.com": "Narinder Singh",
  "rahul.dhiman1@prth.com": "Rahul Kumar Dhiman",
  "vikram.tanwar@prth.com": "Vikram Tanwar",
  "nitin.mehra@prth.com": "Nitin Mehra",
  "amit.rana@prth.com": "Amit Rana",
  "simran.s@prth.com": "Simran S",
  "varun.dogra@prth.com": "Varun Dogra",
  "shomik.dasgupta@prth.com": "Shomik Dasgupta",
  "atish.mukherjee@prth.com": "Atish Mukherjee"
};
const BULK_PAYMENT_FIELDS = [
  "subscriber",
  "clientId",
  "clientFullName",
  "dmPaymentScheduleId",
  "dmPaymentScheduleCount",
  "paymentDueDateNew",
  "paymentAmount",
  "creditorName",
  "credContactWorkNumber",
  "currentAccountNumbers",
  "originalAccountNumber",
  "credEmailAddress",
  "routingNumber",
  "checkingAccountNumber",
  "agentName",
  "paymentSetupMode",
  "ringCentralMasterId",
  "receivedOnDate",
  "comments",
  "termBreakdown",
  "totalPaymentSetup",
  "paymentOutcome",
  "isFollowupRequired",
  "followupDate"
];
const AGENT_ASSIGNMENT_HEADERS = [
  "Assignment ID",
  "Source",
  "Assigned To Email",
  "Assigned To Name",
  "Status",
  "Assigned At",
  "Assigned By",
  "Opened At",
  "Completed At",
  "Client ID",
  "Client Full Name",
  "CRM Payment Schedule ID",
  "Payment Due Date",
  "Payment Amount",
  "Creditor Name",
  "DEBT_ACCOUNT_NUMBER",
  "ORIGINAL_ACCOUNT_NUMBER",
  "Follow up Date",
  "Comments"
];
const MASTER_HEADERS = [
  "COMPANY",
  "ENROLLMENT_EXTERNAL_ID",
  "CLIENT_FULL_NAME",
  "CFT_PAYMENT_SCHEDULE_ID",
  "CRM_PAYMENT_SCHEDULE_ID",
  "PAYMENT_SCHEDULE_DATE",
  "PAYMENT_AMOUNT",
  "PAYMENT_STATUS",
  "CREDITOR_NAME",
  "CREDITOR_CFTPAY_ID",
  "CREDITOR_CRM_ID",
  "ORIGINAL_CREDITOR_NAME",
  "MEMO",
  "DEBT_ACCOUNT_NUMBER",
  "ORIGINAL_ACCOUNT_NUMBER",
  "STREET_ON_CHECK",
  "ZIP_CODE",
  "CITY",
  "STATE",
  "USER",
  "Routing Number",
  "Checking Account Number",
  "Received on",
  "Comments",
  "Follow up Date",
  "Ring Central Master ID"
];
const MASTER_FIELD_LABELS = {
  subscriber: "COMPANY",
  clientId: "ENROLLMENT_EXTERNAL_ID",
  clientFullName: "CLIENT_FULL_NAME",
  dmPaymentScheduleId: "CRM_PAYMENT_SCHEDULE_ID",
  paymentDueDateNew: "PAYMENT_SCHEDULE_DATE",
  paymentAmount: "PAYMENT_AMOUNT",
  paymentOutcome: "PAYMENT_STATUS",
  creditorName: "CREDITOR_NAME",
  currentAccountNumbers: "DEBT_ACCOUNT_NUMBER",
  originalAccountNumber: "ORIGINAL_ACCOUNT_NUMBER",
  agentName: "USER",
  receivedOnDate: "Received on",
  comments: "Comments",
  followupDate: "Follow up Date",
  ringCentralMasterId: "Ring Central Master ID",
  dmPaymentScheduleCount: "",
  credContactWorkNumber: "",
  credEmailAddress: "",
  routingNumber: "Routing Number",
  checkingAccountNumber: "Checking Account Number",
  termBreakdown: "",
  totalPaymentSetup: "",
  paymentSetupMode: "",
  isFollowupRequired: ""
};
const BULK_PAYMENT_LABELS = MASTER_FIELD_LABELS;
const MASTER_HEADER_RENAMES = {
  "Subscriber": "COMPANY",
  "Client ID": "ENROLLMENT_EXTERNAL_ID",
  "Client Full Name": "CLIENT_FULL_NAME",
  "CFT Payment Schedule ID": "CFT_PAYMENT_SCHEDULE_ID",
  "DM Payment Schedule ID": "CRM_PAYMENT_SCHEDULE_ID",
  "CRM Payment Schedule ID": "CRM_PAYMENT_SCHEDULE_ID",
  "Payment Due Date New": "PAYMENT_SCHEDULE_DATE",
  "Payment Due Date": "PAYMENT_SCHEDULE_DATE",
  "Payment Amount": "PAYMENT_AMOUNT",
  "Payment Status": "PAYMENT_STATUS",
  "Payment Outcome": "PAYMENT_STATUS",
  "Creditor Name": "CREDITOR_NAME",
  "Creditor CFTPay ID": "CREDITOR_CFTPAY_ID",
  "Creditor DM ID": "CREDITOR_CRM_ID",
  "Creditor CRM ID": "CREDITOR_CRM_ID",
  "Original Creditor Name": "ORIGINAL_CREDITOR_NAME",
  "Memo (DM) / User (SF)": "MEMO",
  "Current Account Numbers": "DEBT_ACCOUNT_NUMBER",
  "Debt Account Number": "DEBT_ACCOUNT_NUMBER",
  "Original Account Number": "ORIGINAL_ACCOUNT_NUMBER",
  "Street On Check": "STREET_ON_CHECK",
  "Zip Code": "ZIP_CODE",
  "City": "CITY",
  "State": "STATE",
  "Agent Name": "USER",
  "ABA_NUMBER": "Routing Number",
  "ABA Number": "Routing Number",
  "Routing #": "Routing Number",
  "Routing": "Routing Number",
  "BANK_ACCOUNT_NUMBER": "Checking Account Number",
  "Bank Account Number": "Checking Account Number",
  "Checking Account #": "Checking Account Number",
  "CFT Team Payment Worked date": "Received on",
  "Payment Received on (Date)": "Received on"
};
const MASTER_DATE_HEADERS = ["PAYMENT_SCHEDULE_DATE", "Received on", "Follow up Date"];

function doGet() {
  if (!isCrmUserAllowed()) return accessDeniedPage();

  return HtmlService
    .createTemplateFromFile("Index")
    .evaluate()
    .setTitle("Payment Entry CRM")
    .setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL);
}

function getCurrentUserEmail() {
  return String(Session.getActiveUser().getEmail() || "").trim().toLowerCase();
}

function normalizeEmail(email) {
  return String(email || "").trim().toLowerCase();
}

function isCrmUserAllowed() {
  const email = getCurrentUserEmail();
  return email && (ALLOWED_CRM_USERS.indexOf(email) !== -1 || CRM_ADMIN_USERS.indexOf(email) !== -1);
}

function isCrmAdmin() {
  const email = getCurrentUserEmail();
  return email && CRM_ADMIN_USERS.indexOf(email) !== -1;
}

function requireCrmAccess() {
  if (!isCrmUserAllowed()) {
    throw new Error("Access denied. Your PRTH email is not approved for this CRM.");
  }
}

function requireCrmAdminAccess() {
  requireCrmAccess();
  if (!isCrmAdmin()) {
    throw new Error("Admin access required.");
  }
}

function getCurrentCrmUser() {
  requireCrmAccess();
  const email = getCurrentUserEmail();
  return getCrmUserProfile_(email);
}

function getAssignableCrmUsers() {
  requireCrmAdminAccess();
  return ALLOWED_CRM_USERS.map(function(email) {
    return getCrmUserProfile_(email);
  }).sort(function(first, second) {
    if (first.isAdmin !== second.isAdmin) return first.isAdmin ? -1 : 1;
    return String(first.name || first.email).localeCompare(String(second.name || second.email));
  });
}

function updateCrmPresence() {
  requireCrmAccess();
  const email = getCurrentUserEmail();
  const profile = getCrmUserProfile_(email);
  const now = Date.now();
  const lock = LockService.getScriptLock();
  if (!lock.tryLock(500)) {
    return [profile];
  }

  try {
    const properties = PropertiesService.getScriptProperties();
    let activeUsers = {};
    try {
      activeUsers = JSON.parse(properties.getProperty(CRM_PRESENCE_PROPERTY_KEY) || "{}");
    } catch (error) {
      activeUsers = {};
    }

    activeUsers[email] = {
      email: profile.email,
      name: profile.name,
      isAdmin: profile.isAdmin,
      lastSeen: now
    };

    Object.keys(activeUsers).forEach(function(activeEmail) {
      if (now - Number(activeUsers[activeEmail].lastSeen || 0) > CRM_PRESENCE_ACTIVE_MS) {
        delete activeUsers[activeEmail];
      }
    });

    properties.setProperty(CRM_PRESENCE_PROPERTY_KEY, JSON.stringify(activeUsers));

    return Object.keys(activeUsers)
      .map(function(activeEmail) { return activeUsers[activeEmail]; })
      .sort(function(first, second) {
        if (first.email === email) return -1;
        if (second.email === email) return 1;
        return String(first.name || first.email).localeCompare(String(second.name || second.email));
      })
      .map(function(user) {
        return {
          email: user.email,
          name: user.name,
          isAdmin: Boolean(user.isAdmin)
        };
      });
  } finally {
    lock.releaseLock();
  }
}

function getCrmUserProfile_(email) {
  const normalizedEmail = String(email || "").trim().toLowerCase();
  return {
    email: normalizedEmail,
    name: CRM_USER_NAMES[normalizedEmail] || normalizedEmail,
    isAdmin: CRM_ADMIN_USERS.indexOf(normalizedEmail) !== -1
  };
}

function accessDeniedPage() {
  const email = getCurrentUserEmail() || "Unknown user";
  return HtmlService
    .createHtmlOutput(
      '<!doctype html><html><head><base target="_top"><style>' +
      'body{font-family:Arial,sans-serif;margin:0;min-height:100vh;display:grid;place-items:center;background:#f8fafc;color:#1f2933}' +
      '.box{max-width:520px;background:#fff;border:1px solid #d6dde8;border-radius:8px;padding:28px;box-shadow:0 12px 28px rgba(31,41,55,.08)}' +
      'h1{margin:0 0 10px;font-size:24px}p{line-height:1.5;color:#64748b}' +
      '</style></head><body><div class="box"><h1>Access denied</h1><p>This CRM is restricted to approved PRTH agents only.</p><p>Signed-in email: <strong>' +
      email +
      '</strong></p><p>Please contact your manager if you need access.</p></div></body></html>'
    )
    .setTitle("Access denied");
}

function include(filename) {
  return HtmlService.createHtmlOutputFromFile(filename).getContent();
}

function lookupClientReference(query) {
  requireCrmAccess();
  const searchValue = normalizeLookupValue_(query);
  const rawSearchValue = String(query || "").trim().replace(/^[`']+/, "");
  if (!searchValue) throw new Error("Enter Client ID.");

  let rows = getCachedClientReferenceLookupRows_(searchValue);
  if (!rows) {
    const ss = getClientReferenceSpreadsheet_();
    const sheet = getClientReferenceSheet_(ss);
    if (!sheet) {
      throw new Error('Client reference data was not found. Create a tab named "' + CLIENT_REFERENCE_SHEET_NAME + '" in the client reference spreadsheet and paste the 85,000-row report there.');
    }

    const lastRow = sheet.getLastRow();
    const lastColumn = sheet.getLastColumn();
    if (lastRow < 2 || lastColumn < 1) {
      throw new Error("Client reference tab does not have data rows yet.");
    }

    const headers = sheet.getRange(1, 1, 1, lastColumn).getDisplayValues()[0].map(function(header) { return String(header || "").trim(); });
    const columns = getClientReferenceColumns_(headers);
    if (!columns.clientId) {
      throw new Error("Client reference tab needs ENROLLMENT_EXTERNAL_ID or Client ID column.");
    }

    function loadMatchingRows_(rowNumbersToLoad) {
      if (!rowNumbersToLoad.length) return [];
      return getClientReferenceRowsByRowNumbers_(sheet, rowNumbersToLoad, lastColumn)
        .map(function(row) {
          return clientReferenceRowToObject_(row, columns);
        })
        .filter(function(row) {
          return row.id && normalizeLookupValue_(row.clientId) === searchValue;
        });
    }

    let rowNumbers = getIndexedClientReferenceRowNumbers_(ss, searchValue, lastRow);
    rows = loadMatchingRows_(rowNumbers);
    if (!rows.length || rows.length !== rowNumbers.length) {
      rowNumbers = getClientReferenceMatchRowNumbers_(sheet, columns, rawSearchValue, searchValue, lastRow);
      rows = loadMatchingRows_(rowNumbers);
    }
    cacheClientReferenceLookupRows_(searchValue, rows);
  }

  const masterRows = getMasterClientLookupRows_(rawSearchValue, searchValue);
  const completedMasterRows = masterRows.filter(isCompletedClientLookupRow_);
  rows = mergeClientLookupRows_(rows, masterRows);
  rows = rows.filter(function(row) {
    return !isCompletedClientLookupRow_(row) && !matchesCompletedMasterLookupRow_(row, completedMasterRows);
  });
  const completedRowCount = completedMasterRows.length;

  if (!rows.length) {
    return {
      rows: [],
      totalRows: 0,
      completedRowsHidden: completedRowCount,
      warning: completedRowCount
        ? completedRowCount + " payment row" + (completedRowCount === 1 ? " is" : "s are") + " already setup and hidden from the active work list."
        : ""
    };
  }

  rows.sort(function(first, second) {
    const firstDate = parseUsDate(first.dueDate);
    const secondDate = parseUsDate(second.dueDate);
    if (firstDate && secondDate) return firstDate - secondDate;
    return String(first.dueDate || "").localeCompare(String(second.dueDate || ""));
  });

  const maxRows = 250;
  const limitedRows = rows.slice(0, maxRows);
  const result = {
    rows: limitedRows,
    totalRows: rows.length,
    completedRowsHidden: completedRowCount,
    warning: buildClientReferenceLookupWarning_(rows.length, maxRows, completedRowCount)
  };
  return result;
}

function getCachedClientReferenceLookupRows_(searchValue) {
  try {
    const cached = CacheService.getScriptCache().get("client-ref:" + searchValue);
    return cached ? JSON.parse(cached) : null;
  } catch (error) {
    return null;
  }
}

function cacheClientReferenceLookupRows_(searchValue, rows) {
  try {
    const payload = JSON.stringify(rows || []);
    if (payload.length < 90000) {
      CacheService.getScriptCache().put("client-ref:" + searchValue, payload, 300);
    }
  } catch (error) {
    // Cache is only a speed helper. Lookup should continue normally if it fails.
  }
}

function getMasterClientLookupRows_(rawSearchValue, normalizedSearchValue) {
  try {
    const ss = getTargetSpreadsheet();
    const sheet = ss.getSheetByName(SHEET_NAME);
    if (!sheet || sheet.getLastRow() < 2 || sheet.getLastColumn() < 1) return [];

    const lastRow = sheet.getLastRow();
    const lastColumn = sheet.getLastColumn();
    const headers = sheet.getRange(1, 1, 1, lastColumn).getDisplayValues()[0].map(function(header) {
      return String(header || "").trim();
    });
    const columns = getClientReferenceColumns_(headers);
    if (!columns.clientId) return [];

    const rowNumbers = getClientReferenceMatchRowNumbers_(sheet, columns, rawSearchValue, normalizedSearchValue, lastRow);
    if (!rowNumbers.length) return [];

    return getClientReferenceRowsByRowNumbers_(sheet, rowNumbers, lastColumn)
      .map(function(row) {
        return clientReferenceRowToObject_(row, columns);
      })
      .filter(function(row) {
        return row.id && normalizeLookupValue_(row.clientId) === normalizedSearchValue;
      });
  } catch (error) {
    return [];
  }
}

function mergeClientLookupRows_(referenceRows, masterRows) {
  const mergedRows = [];
  const rowMap = {};

  function mergeRow_(row, preferNewValue) {
    const scheduleKey = normalizeLookupValue_(row && row.id);
    if (!scheduleKey) return;

    if (!rowMap[scheduleKey]) {
      rowMap[scheduleKey] = Object.assign({}, row);
      mergedRows.push(rowMap[scheduleKey]);
      return;
    }

    const target = rowMap[scheduleKey];
    Object.keys(row).forEach(function(key) {
      const value = row[key];
      const hasValue = value !== null && value !== undefined && String(value).trim() !== "";
      if (!hasValue) return;
      if (preferNewValue || !String(target[key] || "").trim()) target[key] = value;
    });
  }

  (referenceRows || []).forEach(function(row) {
    mergeRow_(row, false);
  });
  (masterRows || []).forEach(function(row) {
    mergeRow_(row, true);
  });

  return mergedRows;
}

function isCompletedClientLookupRow_(row) {
  const status = String(row && row.paymentStatus || "").trim().toLowerCase();
  const followup = String(row && row.followupDate || "").trim().toUpperCase();
  const setupCompleted = status === "payment setup completed" || status === "bulk payments setup successfully";
  return setupCompleted && followup === "N/A";
}

function matchesCompletedMasterLookupRow_(row, completedMasterRows) {
  if (!row || !(completedMasterRows || []).length) return false;
  const rowScheduleKey = normalizeLookupValue_(row.id);
  const rowDueDate = normalizeUsDate(row.dueDate);
  const rowAmount = normalizeBulkAmount_(row.amount);
  const rowCreditor = normalizeLookupValue_(row.creditorName);
  const rowDebtAccount = normalizeLookupValue_(row.currentAccountNumbers);
  const rowOriginalAccount = normalizeLookupValue_(row.originalAccountNumber);

  return completedMasterRows.some(function(masterRow) {
    const masterScheduleKey = normalizeLookupValue_(masterRow.id);
    if (rowScheduleKey && masterScheduleKey && rowScheduleKey === masterScheduleKey) return true;

    const masterDueDate = normalizeUsDate(masterRow.dueDate);
    if (!rowDueDate || !masterDueDate || rowDueDate !== masterDueDate) return false;

    const masterAmount = normalizeBulkAmount_(masterRow.amount);
    if (rowAmount && masterAmount && rowAmount !== masterAmount) return false;

    const masterCreditor = normalizeLookupValue_(masterRow.creditorName);
    if (rowCreditor && masterCreditor && rowCreditor !== masterCreditor) return false;

    const masterDebtAccount = normalizeLookupValue_(masterRow.currentAccountNumbers);
    const masterOriginalAccount = normalizeLookupValue_(masterRow.originalAccountNumber);
    const rowHasAccount = rowDebtAccount || rowOriginalAccount;
    const masterHasAccount = masterDebtAccount || masterOriginalAccount;
    if (!rowHasAccount || !masterHasAccount) return true;

    return Boolean(
      (rowDebtAccount && (rowDebtAccount === masterDebtAccount || rowDebtAccount === masterOriginalAccount))
        || (rowOriginalAccount && (rowOriginalAccount === masterOriginalAccount || rowOriginalAccount === masterDebtAccount))
    );
  });
}

function findClientReferenceRowNumber_(sheet, column, rawSearchValue, normalizedSearchValue, lastRow) {
  if (!column || lastRow < 2) return 0;
  const range = sheet.getRange(2, column, lastRow - 1, 1);
  if (rawSearchValue) {
    const finder = range.createTextFinder(rawSearchValue).matchEntireCell(true).matchCase(false);
    const cell = finder.findNext();
    if (cell) return cell.getRow();
  }

  const values = range.getDisplayValues();
  for (let index = 0; index < values.length; index += 1) {
    if (normalizeLookupValue_(values[index][0]) === normalizedSearchValue) return index + 2;
  }
  return 0;
}

function getClientReferenceMatchRowNumbers_(sheet, columns, rawClientId, normalizedClientId, lastRow) {
  if (!columns.clientId || !normalizedClientId) return [];
  const range = sheet.getRange(2, columns.clientId, lastRow - 1, 1);
  const cells = range.createTextFinder(String(rawClientId)).matchEntireCell(true).matchCase(false).findAll();
  if (cells && cells.length) return cells.map(function(cell) { return cell.getRow(); });

  const values = range.getDisplayValues();
  const rowNumbers = [];
  values.forEach(function(row, index) {
    if (normalizeLookupValue_(row[0]) === normalizedClientId) rowNumbers.push(index + 2);
  });
  return rowNumbers;
}

function getIndexedClientReferenceRowNumbers_(ss, normalizedClientId, sourceLastRow) {
  const indexSheet = ss.getSheetByName(CLIENT_REFERENCE_INDEX_SHEET_NAME);
  if (!indexSheet || indexSheet.getLastRow() < 2) return [];
  const finder = indexSheet
    .getRange(2, 1, indexSheet.getLastRow() - 1, 1)
    .createTextFinder(normalizedClientId)
    .matchEntireCell(true)
    .matchCase(false);
  const cell = finder.findNext();
  if (!cell) return [];
  const rowNumbersText = String(indexSheet.getRange(cell.getRow(), 2).getDisplayValue() || "");
  const rowNumbers = rowNumbersText
    .split(",")
    .map(function(value) { return Number(value.trim()); })
    .filter(function(value) { return Number.isInteger(value) && value > 1; });
  const indexedPaymentRowCount = Number(indexSheet.getRange(cell.getRow(), 3).getDisplayValue() || 0);
  if (indexedPaymentRowCount && indexedPaymentRowCount !== rowNumbers.length) return [];
  return rowNumbers;
}

function getClientReferenceRowsByRowNumbers_(sheet, rowNumbers, lastColumn) {
  const sortedRows = rowNumbers
    .slice()
    .sort(function(first, second) { return first - second; });
  const rows = [];
  let startRow = 0;
  let previousRow = 0;

  function flushRange_() {
    if (!startRow) return;
    const count = previousRow - startRow + 1;
    const values = sheet.getRange(startRow, 1, count, lastColumn).getDisplayValues();
    values.forEach(function(row) { rows.push(row); });
  }

  sortedRows.forEach(function(rowNumber) {
    if (!startRow) {
      startRow = rowNumber;
      previousRow = rowNumber;
      return;
    }
    if (rowNumber === previousRow + 1) {
      previousRow = rowNumber;
      return;
    }
    flushRange_();
    startRow = rowNumber;
    previousRow = rowNumber;
  });
  flushRange_();
  return rows;
}

function buildClientReferenceLookupWarning_(rowCount, maxRows, completedRowCount) {
  const messages = [];
  if (rowCount > maxRows) {
    messages.push("This client has " + rowCount + " schedule rows. The CRM loaded the first " + maxRows + " rows only.");
  }
  if (completedRowCount) {
    messages.push(completedRowCount + " already setup payment row" + (completedRowCount === 1 ? " was" : "s were") + " hidden from the active work list.");
  }
  return messages.join(" ");
}

function getClientReferenceColumns_(headers) {
  return {
    subscriber: getBulkColumn_(headers, ["COMPANY", "Subscriber"]),
    clientId: getBulkColumn_(headers, ["ENROLLMENT_EXTERNAL_ID", "Client ID", "Client Id"]),
    clientFullName: getBulkColumn_(headers, ["CLIENT_FULL_NAME", "Client Full Name", "Client Name"]),
    cftPaymentScheduleId: getBulkColumn_(headers, ["CFT_PAYMENT_SCHEDULE_ID", "CFT Payment Schedule ID"]),
    dmPaymentScheduleId: getBulkColumn_(headers, ["CRM_PAYMENT_SCHEDULE_ID", "CRM Payment Schedule ID", "DM Payment Schedule ID", "Schedule ID"]),
    dueDate: getBulkColumn_(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date New", "Payment Due Date", "Due Date"]),
    amount: getBulkColumn_(headers, ["PAYMENT_AMOUNT", "Payment Amount", "Amount"]),
    paymentStatus: getBulkColumn_(headers, ["PAYMENT_STATUS", "Payment Status", "Status"]),
    creditorName: getBulkColumn_(headers, ["CREDITOR_NAME", "Creditor Name", "Creditor"]),
    creditorCftpayId: getBulkColumn_(headers, ["CREDITOR_CFTPAY_ID", "Creditor CFTPay ID"]),
    creditorCrmId: getBulkColumn_(headers, ["CREDITOR_CRM_ID", "Creditor CRM ID", "Creditor DM ID"]),
    originalCreditorName: getBulkColumn_(headers, ["ORIGINAL_CREDITOR_NAME", "Original Creditor Name"]),
    memo: getBulkColumn_(headers, ["MEMO", "Memo", "Memo (DM) / User (SF)"]),
    currentAccountNumbers: getBulkColumn_(headers, ["DEBT_ACCOUNT_NUMBER", "Debt Account Number", "Current Account Numbers", "Account Number"]),
    originalAccountNumber: getBulkColumn_(headers, ["ORIGINAL_ACCOUNT_NUMBER", "Original Account Number", "Original Account Numbers"]),
    streetOnCheck: getBulkColumn_(headers, ["STREET_ON_CHECK", "Street On Check"]),
    zipCode: getBulkColumn_(headers, ["ZIP_CODE", "Zip Code", "Zip"]),
    city: getBulkColumn_(headers, ["CITY", "City"]),
    state: getBulkColumn_(headers, ["STATE", "State"]),
    user: getBulkColumn_(headers, ["USER", "User", "Agent Name"]),
    receivedOnDate: getBulkColumn_(headers, ["Received on", "CFT Team Payment Worked date", "Payment Received on (Date)"]),
    comments: getBulkColumn_(headers, ["Comments", "Comment", "Notes"]),
    followupDate: getBulkColumn_(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date"]),
    ringCentralMasterId: getBulkColumn_(headers, ["Ring Central Master ID", "RingCentral Master ID"]),
    routingNumber: getBulkColumn_(headers, ["ABA_NUMBER", "ABA Number", "Routing Number", "Routing #", "Routing"]),
    checkingAccountNumber: getBulkColumn_(headers, ["BANK_ACCOUNT_NUMBER", "Bank Account Number", "Checking Account Number", "Checking ACcount Number", "Checking Acct Number", "Checking Acct#", "Account Number On Check"])
  };
}

function getClientReferenceSheet_(ss) {
  const exactSheet = ss.getSheetByName(CLIENT_REFERENCE_SHEET_NAME);
  if (exactSheet) return exactSheet;

  const sheets = ss.getSheets();
  for (let index = 0; index < sheets.length; index += 1) {
    const sheet = sheets[index];
    const lastColumn = sheet.getLastColumn();
    if (lastColumn < 1 || sheet.getLastRow() < 2) continue;
    const headers = sheet.getRange(1, 1, 1, lastColumn).getDisplayValues()[0].map(function(header) {
      return String(header || "").trim();
    });
    const columns = getClientReferenceColumns_(headers);
    if (columns.clientId && columns.dmPaymentScheduleId && columns.dueDate && columns.amount) return sheet;
  }

  return null;
}

function getClientReferenceSpreadsheet_() {
  if (CLIENT_REFERENCE_SPREADSHEET_ID) return SpreadsheetApp.openById(CLIENT_REFERENCE_SPREADSHEET_ID);
  return getTargetSpreadsheet();
}

function clientReferenceRowToObject_(row, columns) {
  return {
    subscriber: getBulkCell_(row, columns.subscriber),
    clientId: getBulkCell_(row, columns.clientId),
    clientFullName: getBulkCell_(row, columns.clientFullName),
    cftPaymentScheduleId: getBulkCell_(row, columns.cftPaymentScheduleId),
    id: getBulkCell_(row, columns.dmPaymentScheduleId),
    dueDate: normalizeBulkDate_(getBulkCell_(row, columns.dueDate)),
    amount: normalizeBulkAmount_(getBulkCell_(row, columns.amount)),
    paymentStatus: getBulkCell_(row, columns.paymentStatus),
    creditorName: getBulkCell_(row, columns.creditorName),
    creditorCftpayId: getBulkCell_(row, columns.creditorCftpayId),
    creditorCrmId: getBulkCell_(row, columns.creditorCrmId),
    originalCreditorName: getBulkCell_(row, columns.originalCreditorName),
    memo: getBulkCell_(row, columns.memo),
    currentAccountNumbers: cleanAccountNumber_(getBulkCell_(row, columns.currentAccountNumbers)),
    originalAccountNumber: cleanAccountNumber_(getBulkCell_(row, columns.originalAccountNumber)),
    streetOnCheck: getBulkCell_(row, columns.streetOnCheck),
    zipCode: getBulkCell_(row, columns.zipCode),
    city: getBulkCell_(row, columns.city),
    state: getBulkCell_(row, columns.state),
    user: getBulkCell_(row, columns.user),
    receivedOnDate: normalizeBulkDate_(getBulkCell_(row, columns.receivedOnDate)),
    comments: getBulkCell_(row, columns.comments),
    followupDate: normalizeBulkDate_(getBulkCell_(row, columns.followupDate)),
    ringCentralMasterId: getBulkCell_(row, columns.ringCentralMasterId),
    routingNumber: cleanAccountNumber_(getBulkCell_(row, columns.routingNumber)),
    checkingAccountNumber: cleanAccountNumber_(getBulkCell_(row, columns.checkingAccountNumber))
  };
}

function normalizeLookupValue_(value) {
  let text = String(value || "").trim().replace(/^[`']+/, "");
  if (/^\d{1,3}(?:,\d{3})+(?:\.0+)?$/.test(text)) text = text.replace(/,/g, "");
  if (/^\d+\.0+$/.test(text)) text = text.replace(/\.0+$/, "");
  return text.toLowerCase();
}

function savePaymentEntry(contents) {
  requireCrmAccess();
  if (!contents) return { ok: false, message: "No CRM form data received." };
  if (CRM_SYNC_ATTEMPT_LOG_ENABLED) logCrmSyncAttempt_("Single Payment Entry Received", contents);
  try {
    const result = runWithMasterSheetLock_(function() {
      return processPayload(JSON.parse(contents));
    });
    if (CRM_SYNC_ATTEMPT_LOG_ENABLED) logCrmSyncAttempt_("Single Payment Entry Synced", contents, result);
    notifyIfNoRowsUpdated_(result, "Single Payment Entry - No Rows Updated", contents);
    return result;
  } catch (error) {
    notifyCrmSyncError_("Single Payment Entry", error, getCrmSyncDetailsFromContents_(contents));
    throw error;
  }
}

function notifyClientSyncFailure(message, contents) {
  requireCrmAccess();
  const error = new Error(message || "The CRM browser reported that the master sheet did not receive the entry.");
  notifyCrmSyncError_("Client Browser Sync Failure", error, getCrmSyncDetailsFromContents_(contents));
  return { ok: true };
}

function doPost(e) {
  if (!isCrmUserAllowed()) return jsonOutput({ ok: false, message: "Access denied." });
  const contents = getPayloadContents(e);
  if (!contents) return jsonOutput({ ok: false, message: "No CRM form data received." });
  if (CRM_SYNC_ATTEMPT_LOG_ENABLED) logCrmSyncAttempt_("Payment Entry POST Received", contents);
  try {
    const result = runWithMasterSheetLock_(function() {
      return processPayload(JSON.parse(contents));
    });
    if (CRM_SYNC_ATTEMPT_LOG_ENABLED) logCrmSyncAttempt_("Payment Entry POST Synced", contents, result);
    notifyIfNoRowsUpdated_(result, "Payment Entry POST - No Rows Updated", contents);
    return jsonOutput(result);
  } catch (error) {
    notifyCrmSyncError_("Payment Entry POST", error, getCrmSyncDetailsFromContents_(contents));
    return jsonOutput({ ok: false, message: error.message || "Master sheet sync failed." });
  }
}

function notifyIfNoRowsUpdated_(result, context, contents) {
  if (!result || result.ok === false || Number(result.updated || 0) !== 0) return;
  const reason = result.skippedDuplicatePaymentSetups
    ? "No rows were updated because the matching CRM schedule/date was already completed."
    : "No rows were updated in the master sheet.";
  notifyCrmSyncError_(context, new Error(reason), getCrmSyncDetailsFromContents_(contents));
}

function logCrmSyncAttempt_(context, contents, result) {
  try {
    const ss = getTargetSpreadsheet();
    const sheet = ss.getSheetByName("CRM Sync Attempts") || ss.insertSheet("CRM Sync Attempts");
    if (sheet.getLastRow() === 0) {
      sheet.appendRow([
        "Logged At",
        "Context",
        "Active User",
        "Effective User",
        "Client ID",
        "Client Full Name",
        "CRM Payment Schedule IDs",
        "Updated Rows",
        "Skipped Rows"
      ]);
    }
    let record = {};
    try {
      const payload = JSON.parse(contents || "{}");
      record = payload && payload.record ? payload.record : {};
    } catch (error) {
      record = {};
    }
    sheet.appendRow([
      new Date(),
      context,
      getCurrentUserEmail() || "Unknown",
      String(Session.getEffectiveUser().getEmail() || ""),
      String(record.clientId || ""),
      String(record.clientFullName || ""),
      getDmScheduleIds(record).join(", "),
      result ? Number(result.updated || 0) : "",
      result ? Number(result.skippedDuplicatePaymentSetups || 0) : ""
    ]);
  } catch (logError) {
    console.error("CRM sync attempt log failed: " + (logError && logError.message ? logError.message : logError));
  }
}

function saveBulkPaymentEntriesFromRows(sourceValues, dashboardOptions) {
  requireCrmAccess();
  try {
    return runWithMasterSheetLock_(function() {
      const payloads = buildBulkPaymentPayloads_(sourceValues || [], dashboardOptions || {});
      if (!payloads.length) throw new Error("No valid payment rows were found in the uploaded Excel file.");

      let syncedRows = 0;
      payloads.forEach(function(payload) {
        const result = processPayload(payload);
        syncedRows += Number(result.updated || 0);
      });

      const result = {
        ok: true,
        clients: payloads.length,
        syncedRows: syncedRows,
        syncedAt: new Date().toISOString()
      };
      if (!syncedRows) {
        notifyCrmSyncError_("Bulk Excel Upload - No Rows Updated", new Error("Bulk upload finished but no master sheet rows were updated."), getCrmSyncDetailsFromBulkRows_(sourceValues, dashboardOptions));
      }
      return result;
    });
  } catch (error) {
    notifyCrmSyncError_("Bulk Excel Upload", error, getCrmSyncDetailsFromBulkRows_(sourceValues, dashboardOptions));
    throw error;
  }
}

function runWithMasterSheetLock_(callback) {
  const lock = LockService.getScriptLock();
  try {
    lock.waitLock(SYNC_LOCK_WAIT_MS);
  } catch (error) {
    throw new Error("CRM sync is busy because another payment entry is saving. Please wait a few seconds and submit again.");
  }

  try {
    const result = callback();
    return result;
  } finally {
    lock.releaseLock();
  }
}

function notifyCrmSyncError_(context, error, details) {
  const message = error && error.message ? error.message : String(error || "Unknown error");
  const stack = error && error.stack ? "\n\nStack:\n" + error.stack : "";
  const body = [
    "A CRM entry did not update in the master sheet.",
    "",
    "Context: " + context,
    "Error: " + message,
    "User: " + (getCurrentUserEmail() || "Unknown"),
    "Effective user: " + String(Session.getEffectiveUser().getEmail() || ""),
    "Time: " + new Date().toString(),
    "Master sheet: " + SHEET_NAME,
    "",
    "Case details:",
    details || "No case details were available.",
    stack
  ].join("\n");
  let notificationStatus = "Email not configured";

  try {
    if (CRM_SYNC_ERROR_EMAILS.length) {
      MailApp.sendEmail({
        to: CRM_SYNC_ERROR_EMAILS.join(","),
        subject: "CRM master sheet sync error - " + context,
        body: body
      });
      notificationStatus = "Email sent to " + CRM_SYNC_ERROR_EMAILS.join(", ");
    }
  } catch (notificationError) {
    notificationStatus = "Email failed: " + (notificationError && notificationError.message ? notificationError.message : notificationError);
    console.error("CRM sync error notification failed: " + notificationStatus);
  }

  logCrmSyncError_(context, message, details, notificationStatus);
}

function logCrmSyncError_(context, message, details, notificationStatus) {
  try {
    const ss = getTargetSpreadsheet();
    const sheet = ss.getSheetByName("CRM Sync Errors") || ss.insertSheet("CRM Sync Errors");
    if (sheet.getLastRow() === 0) {
      sheet.appendRow([
        "Logged At",
        "Context",
        "Error",
        "Active User",
        "Effective User",
        "Notification Status",
        "Details"
      ]);
    }
    sheet.appendRow([
      new Date(),
      context,
      message,
      getCurrentUserEmail() || "Unknown",
      String(Session.getEffectiveUser().getEmail() || ""),
      notificationStatus,
      details || ""
    ]);
  } catch (logError) {
    console.error("CRM sync error log failed: " + (logError && logError.message ? logError.message : logError));
  }
}

function getCrmSyncDetailsFromContents_(contents) {
  try {
    const payload = JSON.parse(contents || "{}");
    return describeCrmSyncPayload_(payload);
  } catch (error) {
    return "Could not read submitted CRM payload. Payload length: " + String(contents || "").length;
  }
}

function describeCrmSyncPayload_(payload) {
  const record = payload && payload.record ? payload.record : {};
  const dmIds = getDmScheduleIds(record);
  return [
    "Subscriber: " + String(record.subscriber || ""),
    "Client ID: " + String(record.clientId || ""),
    "Client Full Name: " + String(record.clientFullName || ""),
    "CRM Payment Schedule ID(s): " + (dmIds.length ? dmIds.join(", ") : String(record.dmPaymentScheduleId || "")),
    "Payment Due Date: " + String(record.paymentDueDateNew || ""),
    "Payment Amount: " + String(record.paymentAmount || ""),
    "Creditor Name: " + String(record.creditorName || ""),
    "Agent Name: " + String(record.agentName || ""),
    "Agent Email: " + String(record.agentEmail || ""),
    "Payment Outcome: " + String(record.paymentOutcome || ""),
    "Follow up Date: " + String(record.followupDate || ""),
    "Comments: " + String(record.comments || "").slice(0, 1000)
  ].join("\n");
}

function getCrmSyncDetailsFromBulkRows_(sourceValues, dashboardOptions) {
  const rows = Array.isArray(sourceValues) ? sourceValues : [];
  const headers = rows.length ? rows[0].map(String) : [];
  const scheduleColumn = getBulkColumn_(headers, ["CRM_PAYMENT_SCHEDULE_ID", "CRM Payment Schedule ID", "DM Payment Schedule ID", "CRM Schedule ID", "Schedule ID"]);
  const clientIdColumn = getBulkColumn_(headers, ["ENROLLMENT_EXTERNAL_ID", "Client ID"]);
  const clientNameColumn = getBulkColumn_(headers, ["CLIENT_FULL_NAME", "Client Full Name", "Client Name"]);
  const scheduleIds = rows.slice(1, 11).map(function(row) {
    return scheduleColumn ? String(row[scheduleColumn - 1] || "").trim() : "";
  }).filter(Boolean);
  const clients = {};
  rows.slice(1).forEach(function(row) {
    const clientId = clientIdColumn ? String(row[clientIdColumn - 1] || "").trim() : "";
    const clientName = clientNameColumn ? String(row[clientNameColumn - 1] || "").trim() : "";
    const key = [clientId, clientName].join(" / ").trim();
    if (key) clients[key] = true;
  });
  return [
    "Bulk rows received: " + Math.max(rows.length - 1, 0),
    "Client count detected: " + Object.keys(clients).length,
    "First CRM Payment Schedule IDs: " + (scheduleIds.length ? scheduleIds.join(", ") : "None detected"),
    "Dashboard outcome: " + String(dashboardOptions && dashboardOptions.paymentOutcome || ""),
    "Per-client options: " + String(Boolean(dashboardOptions && dashboardOptions.clientOptions && dashboardOptions.clientOptions.length))
  ].join("\n");
}

function processPayload(payload) {
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME) || ss.insertSheet(SHEET_NAME);
  const fields = payload.fields || [];
  const labels = Object.assign({}, payload.labels || {}, MASTER_FIELD_LABELS);
  const record = payload.record || {};
  const currentUser = getCurrentCrmUser();
  record.agentName = currentUser.name;
  record.agentEmail = currentUser.email;
  const headers = ensureHeaders(sheet, MASTER_HEADERS);
  const dmIds = getDmScheduleIds(record);
  if (!dmIds.length) throw new Error("No CRM Payment Schedule ID was received from the CRM form.");
  ensureUniqueScheduleIds_(dmIds);
  ensurePaymentSetupWithinTerm_(record, dmIds.length);
  const dmColumn = getScheduleIdColumn(headers);
  const dmRowMap = getDmScheduleRowMapForIds(sheet, dmColumn, dmIds);

  const dmDueDates = getDmScheduleDueDates(record);
  const dmAmounts = getDmScheduleAmounts(record);
  const dmFollowupDates = getDmScheduleFollowupDates(record);
  const dmFollowupRequired = getDmScheduleFollowupRequired(record);
  const dmComments = getDmScheduleComments(record);
  const dmMasterValues = getDmScheduleMasterValues(record);
  let updatedRows = 0;
  let skippedDuplicateRows = 0;
  dmIds.forEach(function(dmId, index) {
    const result = upsertDmScheduleRow(
      sheet,
      headers,
      fields,
      labels,
      record,
      dmId,
      dmIds.length,
      index,
      dmDueDates[index],
      dmAmounts[index],
      dmFollowupDates[index],
      dmFollowupRequired[index],
      dmComments[index],
      dmMasterValues[index],
      dmRowMap,
      dmColumn
    );
    if (result && result.skippedDuplicatePaymentSetup) {
      skippedDuplicateRows += 1;
    } else {
      updatedRows += 1;
    }
  });

  return {
    ok: true,
    updated: updatedRows,
    skippedDuplicatePaymentSetups: skippedDuplicateRows,
    syncedAt: new Date().toISOString()
  };
}

function getTargetSpreadsheet() {
  if (SPREADSHEET_ID) return SpreadsheetApp.openById(SPREADSHEET_ID);
  const activeSpreadsheet = SpreadsheetApp.getActiveSpreadsheet();
  if (activeSpreadsheet) return activeSpreadsheet;

  const files = DriveApp.getFilesByName(SPREADSHEET_FILE_NAME);
  if (files.hasNext()) return SpreadsheetApp.openById(files.next().getId());

  throw new Error(
    "Common master sheet was not found. Open the master Google Sheet, copy its spreadsheet ID, and paste it into SPREADSHEET_ID in Code.gs."
  );
}

function testMasterSheetConnection() {
  requireCrmAccess();
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME) || ss.insertSheet(SHEET_NAME);
  let mailStatus = "";
  try {
    mailStatus = "Mail OK. Remaining daily quota: " + MailApp.getRemainingDailyQuota();
  } catch (error) {
    mailStatus = "Mail check failed: " + (error && error.message ? error.message : error);
  }
  const diagnosticsSheet = ss.getSheetByName("CRM Sync Diagnostics") || ss.insertSheet("CRM Sync Diagnostics");
  if (diagnosticsSheet.getLastRow() === 0) {
    diagnosticsSheet.appendRow(["Checked At", "Active User", "Effective User", "Status", "Master Sheet", "Mail Status"]);
  }
  diagnosticsSheet.appendRow([
    new Date(),
    getCurrentUserEmail(),
    String(Session.getEffectiveUser().getEmail() || ""),
    "Connection OK",
    sheet.getName(),
    mailStatus
  ]);
  return {
    ok: true,
    spreadsheetName: ss.getName(),
    spreadsheetId: ss.getId(),
    sheetName: sheet.getName(),
    mailStatus: mailStatus,
    activeUser: getCurrentUserEmail(),
    effectiveUser: String(Session.getEffectiveUser().getEmail() || ""),
    checkedAt: new Date().toISOString()
  };
}

function testClientReferenceConnection() {
  requireCrmAccess();
  const ss = getClientReferenceSpreadsheet_();
  const sheet = getClientReferenceSheet_(ss);
  if (!sheet) {
    throw new Error('Client reference sheet was not found. The tab name should be "' + CLIENT_REFERENCE_SHEET_NAME + '" or the header row must include ENROLLMENT_EXTERNAL_ID and CRM_PAYMENT_SCHEDULE_ID.');
  }

  const lastRow = sheet.getLastRow();
  const lastColumn = sheet.getLastColumn();
  const headers = lastColumn
    ? sheet.getRange(1, 1, 1, lastColumn).getDisplayValues()[0].map(function(header) { return String(header || "").trim(); })
    : [];
  const columns = getClientReferenceColumns_(headers);
  const indexSheet = ss.getSheetByName(CLIENT_REFERENCE_INDEX_SHEET_NAME);
  const sampleRow = lastRow >= 2
    ? sheet.getRange(2, 1, 1, lastColumn).getDisplayValues()[0]
    : [];
  const result = {
    ok: true,
    referenceSpreadsheetName: ss.getName(),
    referenceSpreadsheetId: ss.getId(),
    referenceSheetName: sheet.getName(),
    totalRowsIncludingHeader: lastRow,
    dataRows: Math.max(0, lastRow - 1),
    headerCount: headers.length,
    clientIdColumnFound: Boolean(columns.clientId),
    crmScheduleIdColumnFound: Boolean(columns.dmPaymentScheduleId),
    paymentDateColumnFound: Boolean(columns.dueDate),
    paymentAmountColumnFound: Boolean(columns.amount),
    clientReferenceIndexFound: Boolean(indexSheet),
    clientReferenceIndexRows: indexSheet ? Math.max(0, indexSheet.getLastRow() - 1) : 0,
    sampleClientId: columns.clientId && sampleRow.length ? sampleRow[columns.clientId - 1] : "",
    sampleCrmScheduleId: columns.dmPaymentScheduleId && sampleRow.length ? sampleRow[columns.dmPaymentScheduleId - 1] : "",
    checkedAt: new Date().toISOString()
  };
  Logger.log(JSON.stringify(result, null, 2));
  return result;
}

function rebuildClientReferenceIndex() {
  requireCrmAdminAccess();
  const ss = getClientReferenceSpreadsheet_();
  const sheet = getClientReferenceSheet_(ss);
  if (!sheet) {
    throw new Error('Client reference sheet was not found. The tab name should be "' + CLIENT_REFERENCE_SHEET_NAME + '".');
  }

  const lastRow = sheet.getLastRow();
  const lastColumn = sheet.getLastColumn();
  if (lastRow < 2 || lastColumn < 1) {
    throw new Error("Client reference tab does not have data rows yet.");
  }

  const headers = sheet.getRange(1, 1, 1, lastColumn).getDisplayValues()[0].map(function(header) { return String(header || "").trim(); });
  const columns = getClientReferenceColumns_(headers);
  if (!columns.clientId) {
    throw new Error("Client reference tab needs ENROLLMENT_EXTERNAL_ID or Client ID column before the index can be built.");
  }

  const clientValues = sheet.getRange(2, columns.clientId, lastRow - 1, 1).getDisplayValues();
  const indexMap = {};
  clientValues.forEach(function(row, index) {
    const clientId = normalizeLookupValue_(row[0]);
    if (!clientId) return;
    if (!indexMap[clientId]) indexMap[clientId] = [];
    indexMap[clientId].push(index + 2);
  });

  let indexSheet = ss.getSheetByName(CLIENT_REFERENCE_INDEX_SHEET_NAME);
  if (!indexSheet) indexSheet = ss.insertSheet(CLIENT_REFERENCE_INDEX_SHEET_NAME);
  indexSheet.clear();
  indexSheet.getRange(1, 1, 1, 6).setValues([[
    "CLIENT_ID",
    "ROW_NUMBERS",
    "PAYMENT_ROW_COUNT",
    "SOURCE_SHEET",
    "SOURCE_LAST_ROW",
    "UPDATED_AT"
  ]]);

  const now = new Date();
  const indexRows = Object.keys(indexMap)
    .sort()
    .map(function(clientId) {
      return [
        clientId,
        indexMap[clientId].join(","),
        indexMap[clientId].length,
        sheet.getName(),
        lastRow,
        now
      ];
    });

  for (let start = 0; start < indexRows.length; start += 5000) {
    const chunk = indexRows.slice(start, start + 5000);
    indexSheet.getRange(start + 2, 1, chunk.length, 6).setValues(chunk);
  }

  try {
    indexSheet.hideSheet();
  } catch (error) {
    // Ignore if Google Sheets does not allow hiding in this context.
  }

  return {
    ok: true,
    sourceSheetName: sheet.getName(),
    sourceRows: lastRow - 1,
    indexedClientCount: indexRows.length,
    indexSheetName: indexSheet.getName(),
    rebuiltAt: now.toISOString()
  };
}

function applyNewMasterHeaderFormat() {
  requireCrmAdminAccess();
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME) || ss.insertSheet(SHEET_NAME);
  const headers = ensureHeaders(sheet, MASTER_HEADERS);
  return {
    ok: true,
    sheetName: sheet.getName(),
    headerCount: headers.length,
    appliedAt: new Date().toISOString()
  };
}

function createCurrentMonthFollowupArchive() {
  requireCrmAdminAccess();
  return runWithMasterSheetLock_(function() {
    return copyFollowupRowsToMonthlyArchive_(new Date());
  });
}

function setupMonthlyFollowupArchiveTrigger() {
  requireCrmAdminAccess();
  ScriptApp.getProjectTriggers().forEach(function(trigger) {
    if (trigger.getHandlerFunction() === MONTHLY_FOLLOWUP_ARCHIVE_TRIGGER) {
      ScriptApp.deleteTrigger(trigger);
    }
  });
  ScriptApp.newTrigger(MONTHLY_FOLLOWUP_ARCHIVE_TRIGGER)
    .timeBased()
    .onMonthDay(1)
    .atHour(3)
    .create();
  return {
    ok: true,
    message: "Monthly follow-up archive trigger is active.",
    handler: MONTHLY_FOLLOWUP_ARCHIVE_TRIGGER
  };
}

function monthlyFollowupArchiveTrigger() {
  return runWithMasterSheetLock_(function() {
    return copyFollowupRowsToMonthlyArchive_(new Date());
  });
}

function copyFollowupRowsToMonthlyArchive_(targetDate) {
  const sourceSpreadsheet = getTargetSpreadsheet();
  const sourceSheet = sourceSpreadsheet.getSheetByName(SHEET_NAME);
  const archiveName = monthlyFollowupArchiveName_(targetDate);
  if (!sourceSheet || sourceSheet.getLastRow() < 2) {
    return logMonthlyFollowupArchive_(sourceSpreadsheet, {
      ok: true,
      spreadsheetName: archiveName,
      rowsCopied: 0,
      rowsInserted: 0,
      rowsUpdated: 0,
      message: "No master rows found."
    });
  }

  const sourceValues = sourceSheet.getRange(1, 1, sourceSheet.getLastRow(), sourceSheet.getLastColumn()).getValues();
  const headers = sourceValues[0].map(String);
  const followupColumn = getHeaderColumn(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]);
  if (!followupColumn) throw new Error("Master sheet does not have Follow up Date column.");

  const targetMonth = targetDate.getMonth();
  const targetYear = targetDate.getFullYear();
  const rowsToCopy = sourceValues.slice(1).filter(function(row) {
    const followupDate = parseUsDate(normalizeUsDate(row[followupColumn - 1]));
    return followupDate && followupDate.getMonth() === targetMonth && followupDate.getFullYear() === targetYear;
  });

  const archiveSpreadsheet = getOrCreateSpreadsheetByName_(archiveName);
  const archiveSheet = archiveSpreadsheet.getSheetByName(MONTHLY_FOLLOWUP_ARCHIVE_SHEET_NAME)
    || archiveSpreadsheet.insertSheet(MONTHLY_FOLLOWUP_ARCHIVE_SHEET_NAME);
  const archiveHeaders = ensureHeaders(archiveSheet, headers);
  const archiveScheduleColumn = getScheduleIdColumn(archiveHeaders);
  const archiveRowMap = archiveScheduleColumn ? getDmScheduleRowMap(archiveSheet, archiveScheduleColumn) : {};

  let inserted = 0;
  let updated = 0;
  rowsToCopy.forEach(function(sourceRow) {
    const targetRow = archiveHeaders.map(function(header) {
      const sourceIndex = headers.indexOf(header);
      return sourceIndex >= 0 ? sourceRow[sourceIndex] : "";
    });
    const scheduleId = archiveScheduleColumn ? String(targetRow[archiveScheduleColumn - 1] || "").trim().toLowerCase() : "";
    const existingRow = scheduleId ? archiveRowMap[scheduleId] : null;
    const rowNumber = existingRow || archiveSheet.getLastRow() + 1;
    archiveSheet.getRange(rowNumber, 1, 1, archiveHeaders.length).setValues([targetRow]);
    if (existingRow) {
      updated += 1;
    } else {
      inserted += 1;
      if (scheduleId) archiveRowMap[scheduleId] = rowNumber;
    }
  });

  if (archiveSheet.getLastRow() > 0) {
    archiveSheet.setFrozenRows(1);
    archiveSheet.autoResizeColumns(1, archiveHeaders.length);
  }

  return logMonthlyFollowupArchive_(sourceSpreadsheet, {
    ok: true,
    spreadsheetName: archiveName,
    spreadsheetUrl: archiveSpreadsheet.getUrl(),
    rowsCopied: rowsToCopy.length,
    rowsInserted: inserted,
    rowsUpdated: updated,
    message: "Monthly follow-up archive refreshed."
  });
}

function monthlyFollowupArchiveName_(date) {
  const monthNames = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
  return MONTHLY_FOLLOWUP_ARCHIVE_PREFIX + " " + monthNames[date.getMonth()] + " " + String(date.getFullYear());
}

function getOrCreateSpreadsheetByName_(name) {
  const files = DriveApp.getFilesByName(name);
  if (files.hasNext()) return SpreadsheetApp.openById(files.next().getId());
  return SpreadsheetApp.create(name);
}

function logMonthlyFollowupArchive_(sourceSpreadsheet, result) {
  const logSheet = sourceSpreadsheet.getSheetByName("Monthly Archive Log") || sourceSpreadsheet.insertSheet("Monthly Archive Log");
  if (logSheet.getLastRow() === 0) {
    logSheet.appendRow(["Archived At", "Archive Name", "Archive URL", "Rows Copied", "Rows Inserted", "Rows Updated", "Run By", "Message"]);
  }
  logSheet.appendRow([
    new Date(),
    result.spreadsheetName || "",
    result.spreadsheetUrl || "",
    result.rowsCopied || 0,
    result.rowsInserted || 0,
    result.rowsUpdated || 0,
    getCurrentUserEmail() || String(Session.getEffectiveUser().getEmail() || ""),
    result.message || ""
  ]);
  return result;
}

function importOldMasterImportTab() {
  requireCrmAdminAccess();
  return runWithMasterSheetLock_(function() {
    const ss = getTargetSpreadsheet();
    const importSheet = ss.getSheetByName(LEGACY_IMPORT_SHEET_NAME);
    if (!importSheet) {
      throw new Error("Create a tab named '" + LEGACY_IMPORT_SHEET_NAME + "' and paste the old master data there first.");
    }
    return importOldMasterValues_(importSheet.getDataRange().getValues(), LEGACY_IMPORT_SHEET_NAME);
  });
}

function importOldMasterFromConfiguredSpreadsheet() {
  requireCrmAdminAccess();
  if (!OLD_MASTER_SPREADSHEET_ID) {
    throw new Error("Paste the old master spreadsheet ID into OLD_MASTER_SPREADSHEET_ID first.");
  }

  return runWithMasterSheetLock_(function() {
    const oldSpreadsheet = SpreadsheetApp.openById(OLD_MASTER_SPREADSHEET_ID);
    const oldSheet = OLD_MASTER_SHEET_NAME
      ? oldSpreadsheet.getSheetByName(OLD_MASTER_SHEET_NAME)
      : oldSpreadsheet.getSheets()[0];
    if (!oldSheet) throw new Error("Old master sheet tab was not found.");
    return importOldMasterValues_(oldSheet.getDataRange().getValues(), oldSheet.getName());
  });
}

function importOldMasterValues_(sourceValues, sourceName) {
  if (!sourceValues || sourceValues.length < 2) {
    throw new Error("No old master rows were found to import.");
  }

  const targetSpreadsheet = getTargetSpreadsheet();
  const targetSheet = targetSpreadsheet.getSheetByName(SHEET_NAME) || targetSpreadsheet.insertSheet(SHEET_NAME);
  const sourceHeaders = sourceValues[0].map(function(header) { return String(header || "").trim(); });
  const scheduleColumn = getLegacyImportColumn_(sourceHeaders, [
    "CRM_PAYMENT_SCHEDULE_ID",
    "CRM Payment Schedule ID",
    "DM Payment Schedule ID",
    "DM Payment Schedule Id",
    "CRM Schedule ID",
    "CRM Scheduled ID",
    "DM Schedule ID",
    "DM Scheduled ID",
    "Payment Schedule ID",
    "Schedule ID",
    "Scheduled ID"
  ]);
  if (!scheduleColumn) {
    throw new Error("Old master import needs a CRM Payment Schedule ID or DM Payment Schedule ID column.");
  }

  const standardHeaders = MASTER_HEADERS;
  const targetHeaders = ensureHeaders(targetSheet, standardHeaders);
  const targetLastRow = targetSheet.getLastRow();
  const targetRows = targetLastRow > 1
    ? targetSheet.getRange(2, 1, targetLastRow - 1, targetHeaders.length).getValues().map(function(row) {
        while (row.length < targetHeaders.length) row.push("");
        return row;
      })
    : [];

  const targetScheduleColumn = getScheduleIdColumn(targetHeaders);
  if (!targetScheduleColumn) throw new Error("New CRM master sheet is missing CRM Payment Schedule ID column.");

  const targetRowMap = {};
  targetRows.forEach(function(row, index) {
    const key = String(row[targetScheduleColumn - 1] || "").trim().toLowerCase();
    if (key && targetRowMap[key] === undefined) targetRowMap[key] = index;
  });

  let imported = 0;
  let updated = 0;
  let skipped = 0;

  sourceValues.slice(1).forEach(function(sourceRow) {
    if (!sourceRow.some(function(value) { return String(value || "").trim(); })) return;
    const scheduleId = String(sourceRow[scheduleColumn - 1] || "").trim();
    if (!scheduleId) {
      skipped += 1;
      return;
    }

    const key = scheduleId.toLowerCase();
    let targetIndex = targetRowMap[key];
    let isUpdate = true;
    if (targetIndex === undefined) {
      targetRows.push(new Array(targetHeaders.length).fill(""));
      targetIndex = targetRows.length - 1;
      targetRowMap[key] = targetIndex;
      isUpdate = false;
    }

    const targetRow = targetRows[targetIndex];
    BULK_PAYMENT_FIELDS.forEach(function(field) {
      const value = getLegacyImportFieldValue_(sourceRow, sourceHeaders, field);
      const header = getMasterFieldHeader_(field, BULK_PAYMENT_LABELS);
      if (header && value !== "") setImportValue_(targetRow, targetHeaders, header, value);
    });

    const followupDate = getLegacyImportFieldValue_(sourceRow, sourceHeaders, "followupDate");
    const followupRequired = getLegacyImportFieldValue_(sourceRow, sourceHeaders, "isFollowupRequired")
      || (followupDate && String(followupDate).trim().toUpperCase() !== "N/A" ? "Yes" : "No");
    if (followupDate) {
      setImportValue_(targetRow, targetHeaders, "Follow up Date", followupDate);
    }

    sourceHeaders.forEach(function(header, sourceIndex) {
      if (!header) return;
      const targetColumn = targetHeaders.indexOf(header);
      if (targetColumn < 0) return;
      const value = formatLegacyImportCell_(sourceRow[sourceIndex]);
      if (value !== "" && targetRow[targetColumn] === "") {
        targetRow[targetColumn] = formatImportValueForHeader_(header, value);
      }
    });

    if (isUpdate) updated += 1;
    else imported += 1;
  });

  if (targetRows.length) {
    targetSheet.getRange(2, 1, targetRows.length, targetHeaders.length).setValues(targetRows);
  }

  const logSheet = targetSpreadsheet.getSheetByName("CRM Import Log") || targetSpreadsheet.insertSheet("CRM Import Log");
  if (logSheet.getLastRow() === 0) {
    logSheet.appendRow(["Imported At", "Source", "New Rows", "Updated Rows", "Skipped Rows", "Run By"]);
  }
  logSheet.appendRow([new Date(), sourceName || "", imported, updated, skipped, getCurrentUserEmail()]);

  return {
    ok: true,
    source: sourceName || "",
    imported: imported,
    updated: updated,
    skipped: skipped,
    totalProcessed: imported + updated,
    targetSheet: targetSheet.getName()
  };
}

function getFollowupRowsBySelection(selection) {
  requireCrmAccess();
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME);
  if (!sheet || sheet.getLastRow() < 2) return { headers: [], rows: [] };

  const values = sheet.getRange(1, 1, sheet.getLastRow(), sheet.getLastColumn()).getValues();
  const headers = values[0].map(String);
  const followupColumn = getHeaderColumn(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]);
  if (!followupColumn) return { headers: headers, rows: [] };
  const paymentDueColumn = getHeaderColumn(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New"]);

  const targetDates = selection && selection.type === "dates"
    ? (selection.dates || []).map(normalizeUsDate).filter(Boolean)
    : [];
  const targetMonth = selection && selection.type === "month" ? String(selection.month || "") : "";
  const rangeStart = selection && (selection.type === "range" || selection.type === "combined") ? parseUsDate(selection.startDate) : null;
  const rangeEnd = selection && (selection.type === "range" || selection.type === "combined") ? parseUsDate(selection.endDate) : null;
  const paymentDueStart = selection && selection.paymentDueStartDate ? parseUsDate(selection.paymentDueStartDate) : null;
  const paymentDueEnd = selection && selection.paymentDueEndDate ? parseUsDate(selection.paymentDueEndDate) : null;
  const hasPaymentDueRange = Boolean(paymentDueStart && paymentDueEnd && paymentDueColumn);
  const hasFollowupRange = Boolean(rangeStart && rangeEnd);
  const rows = values.slice(1).filter(function(row) {
    const rowDate = normalizeUsDate(row[followupColumn - 1]);
    let followupMatches = false;
    if (rowDate && targetDates.length) followupMatches = targetDates.indexOf(rowDate) !== -1;
    else if (rowDate && targetMonth) followupMatches = usDateToMonthKey(rowDate) === targetMonth;
    else if (rowDate && hasFollowupRange) {
      const parsedRowDate = parseUsDate(rowDate);
      followupMatches = Boolean(parsedRowDate && parsedRowDate >= rangeStart && parsedRowDate <= rangeEnd);
    }
    const blankFollowup = !String(row[followupColumn - 1] || "").trim();
    let dueMatches = true;
    if (hasPaymentDueRange) {
      const dueDate = parseUsDate(normalizeUsDate(row[paymentDueColumn - 1]));
      dueMatches = Boolean(dueDate && dueDate >= paymentDueStart && dueDate <= paymentDueEnd);
    }
    if (hasPaymentDueRange && hasFollowupRange) return dueMatches && (followupMatches || blankFollowup);
    if (hasPaymentDueRange) return dueMatches;
    return followupMatches;
  }).map(function(row) {
    return row.map(function(value, index) {
      return formatSheetCellForHeader(headers[index], value);
    });
  });

  return { headers: headers, rows: rows };
}

function getFollowupRowsByDate(followupDate) {
  return getFollowupRowsBySelection({ type: "dates", dates: [followupDate] });
}

function getFollowupRowsByRange(startDate, endDate) {
  return getFollowupRowsBySelection({ type: "range", startDate: startDate, endDate: endDate });
}

function getAgentWorkedRowsByRange(startDate, endDate) {
  requireCrmAdminAccess();
  const report = getAgentWorkedReportData_(startDate, endDate);
  return { headers: report.headers, rows: report.rows };
}

function getTeamCompletedCountByRange(startDate, endDate) {
  requireCrmAdminAccess();
  const report = getAgentWorkedReportData_(startDate, endDate);
  const workedDateColumn = report.workedDateColumn;
  const agentColumn = report.agentColumn;
  const counts = {};

  report.rawRows.forEach(function(row) {
    const workedDate = normalizeUsDate(row[workedDateColumn - 1]);
    const agentName = String(row[agentColumn - 1] || "Unassigned").trim() || "Unassigned";
    const key = workedDate + "\u0000" + agentName;
    counts[key] = (counts[key] || 0) + 1;
  });

  const rows = Object.keys(counts).sort().map(function(key) {
    const parts = key.split("\u0000");
    return [parts[0], parts[1], counts[key]];
  });

  return {
    headers: ["Worked Date", "Agent Name", "Completed Count"],
    rows: rows
  };
}

function getManagementDashboardData(options) {
  requireCrmAdminAccess();
  options = options || {};
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME);
  const now = new Date();
  const today = new Date(now.getFullYear(), now.getMonth(), now.getDate());
  const tomorrow = new Date(today.getFullYear(), today.getMonth(), today.getDate() + 1);
  const monthStart = new Date(today.getFullYear(), today.getMonth(), 1);
  const monthEnd = new Date(today.getFullYear(), today.getMonth() + 1, 0);
  const selectedDueMonth = parseDashboardDueMonth_(options.dueRange, today);
  const dueMonthStart = new Date(selectedDueMonth.getFullYear(), selectedDueMonth.getMonth(), 1);
  const dueRangeStart = isSameDashboardMonth_(dueMonthStart, today) ? today : dueMonthStart;
  const dueRangeEnd = new Date(selectedDueMonth.getFullYear(), selectedDueMonth.getMonth() + 1, 0);
  const dueMonthLabel = Utilities.formatDate(dueMonthStart, Session.getScriptTimeZone(), "MMM yyyy");
  const followupEnd = dashboardFollowupWindowEnd_(today);
  const asOf = "As of " + Utilities.formatDate(now, Session.getScriptTimeZone(), "MMM d, yyyy h:mm a");

  if (!sheet || sheet.getLastRow() < 2) {
    return {
      title: "JGW CBP Management Dashboard",
      subtitle: "No master sheet data found | " + asOf,
      cards: buildEmptyDashboardCards_(asOf)
    };
  }

  const values = sheet.getRange(1, 1, sheet.getLastRow(), sheet.getLastColumn()).getValues();
  const headers = values[0].map(String);
  const columns = {
    agent: getHeaderColumn(headers, ["USER", "Agent Name"]),
    received: getHeaderColumn(headers, ["Received on", "CFT Team Payment Worked date", "Payment Received on (Date)"]),
    status: getHeaderColumn(headers, ["PAYMENT_STATUS", "Payment Status", "Payment Outcome"]),
    due: getHeaderColumn(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New"]),
    followup: getHeaderColumn(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]),
    creditor: getHeaderColumn(headers, ["CREDITOR_NAME", "Creditor Name", "Creditor"]),
    comments: getHeaderColumn(headers, ["Comments", "Comment", "Notes"])
  };

  const completedTodayByAgent = {};
  const followupsDueToday = {};
  const paymentsSetupMtdByAgent = {};
  const setupModeMtd = {};
  const bulkCreditorsMtd = {};
  const referenceDueCounts = getDashboardReferenceDueCounts_(dueRangeStart, dueRangeEnd, tomorrow);
  const paymentsDueByDate = referenceDueCounts.byDate;
  const paymentsDueTomorrow = referenceDueCounts.tomorrowByCreditor;

  values.slice(1).forEach(function(row) {
    const agent = dashboardValue_(row, columns.agent) || "Unassigned";
    const creditor = dashboardValue_(row, columns.creditor) || "Blank creditor";
    const status = dashboardValue_(row, columns.status);
    const comments = dashboardValue_(row, columns.comments);
    const completed = isDashboardCompleted_(status);
    const receivedDate = parseUsDate(normalizeUsDate(dashboardValue_(row, columns.received)));
    const followupText = dashboardValue_(row, columns.followup);
    const followupDate = parseUsDate(normalizeUsDate(followupText));

    if (completed && isSameDashboardDate_(receivedDate, today)) incrementDashboardCount_(completedTodayByAgent, agent);
    if (followupDate && followupDate >= today && followupDate <= followupEnd) incrementDashboardCount_(followupsDueToday, creditor);
    if (completed && receivedDate && receivedDate >= monthStart && receivedDate <= monthEnd) {
      incrementDashboardCount_(paymentsSetupMtdByAgent, agent);
      incrementDashboardCount_(setupModeMtd, dashboardSetupMode_(comments));
      incrementDashboardCount_(bulkCreditorsMtd, creditor);
    }
  });

  return {
    title: "JGW CBP Management Dashboard",
    subtitle: "Live CRM operating view | " + asOf,
    cards: [
      dashboardTableCard_("Payment Setup Completed Today", "By agent", "USER", completedTodayByAgent, asOf),
      dashboardTableCard_("Follow-ups Due Today", dashboardFollowupSubtitle_(today, followupEnd), "CREDITOR_NAME", followupsDueToday, asOf),
      dashboardBarCardFromRows_(
        "CBP Payments Due " + dueMonthLabel,
        isSameDashboardMonth_(dueMonthStart, today) ? "Today and future dates this month" : "Selected month day wise count",
        dashboardDateRows_(paymentsDueByDate),
        asOf
      ),
      dashboardTableCard_("Payments Setup MTD", "By agent", "USER", paymentsSetupMtdByAgent, asOf),
      dashboardTableCard_("Payments Due Tomorrow", "By creditor", "CREDITOR_NAME", paymentsDueTomorrow, asOf),
      dashboardBarCard_("Setup Mode MTD Volume", "CBP / Web", setupModeMtd, asOf),
      dashboardBarCard_("Bulk Creditors MTD", "Creditor wise count", bulkCreditorsMtd, asOf)
    ]
  };
}

function parseDashboardDueMonth_(value, fallbackDate) {
  const match = String(value || "").match(/^(\d{4})-(\d{2})$/);
  if (match) return new Date(Number(match[1]), Number(match[2]) - 1, 1);
  return new Date(fallbackDate.getFullYear(), fallbackDate.getMonth(), 1);
}

function isSameDashboardMonth_(first, second) {
  return Boolean(first && second
    && first.getFullYear() === second.getFullYear()
    && first.getMonth() === second.getMonth());
}

function exportManagementDashboardReport(reportKey, options) {
  requireCrmAdminAccess();
  const dashboard = getManagementDashboardData(options || {});
  const key = String(reportKey || "").trim();
  const card = (dashboard.cards || []).filter(function(item) {
    return String(item.key || "") === key || String(item.title || "") === key;
  })[0];
  if (!card) throw new Error("Dashboard report was not found. Refresh the dashboard and try again.");

  const ss = getTargetSpreadsheet();
  const sheetName = dashboardReportSheetName_("Dashboard - " + String(card.title || "Report"));
  const sheet = ss.getSheetByName(sheetName) || ss.insertSheet(sheetName);
  sheet.clear();

  const rows = [
    ["Dashboard Report", card.title || ""],
    ["Subtitle", card.subtitle || ""],
    ["Created At", new Date()],
    ["As Of", card.asOf || ""],
    ["", ""],
    [card.labelHeader || "Name", "Record Count"]
  ];
  (card.rows || []).forEach(function(row) {
    rows.push([row.label || "Blank", Number(row.count || 0)]);
  });
  if (!card.rows || !card.rows.length) rows.push(["No data", 0]);

  sheet.getRange(1, 1, rows.length, 2).setValues(rows);
  sheet.getRange(1, 1, 4, 1).setFontWeight("bold").setBackground("#ffffff").setFontColor("#000000");
  sheet.getRange(6, 1, 1, 2).setFontWeight("bold").setBackground("#ffffff").setFontColor("#000000");
  sheet.getRange(1, 1, rows.length, 2).setBorder(true, true, true, true, true, true);
  if (rows.length > 6) sheet.getRange(7, 1, rows.length - 6, 2).setBorder(true, true, true, true, true, true);
  sheet.autoResizeColumns(1, 2);

  return {
    ok: true,
    reportName: sheetName,
    url: ss.getUrl() + "#gid=" + sheet.getSheetId()
  };
}

function dashboardReportSheetName_(baseName) {
  let cleanName = String(baseName || "Dashboard Report").replace(/[\[\]\*\?\/\\:]/g, " ").replace(/\s+/g, " ").trim();
  if (cleanName.length > 99) cleanName = cleanName.slice(0, 99).trim();
  return cleanName || "Dashboard Report";
}

function buildEmptyDashboardCards_(asOf) {
  return [
    { title: "Payment Setup Completed Today", subtitle: "By agent", type: "table", labelHeader: "USER", rows: [], asOf: asOf, linkLabel: "Completed Today" },
    { title: "Follow-ups Due Today", subtitle: "By creditor", type: "table", labelHeader: "CREDITOR_NAME", rows: [], asOf: asOf, linkLabel: "Follow-ups Today" }
  ];
}

function dashboardTableCard_(title, subtitle, labelHeader, counts, asOf) {
  return {
    key: dashboardCardKey_(title),
    title: title,
    subtitle: subtitle,
    type: "table",
    labelHeader: labelHeader,
    rows: dashboardTopRows_(counts, 18),
    asOf: asOf,
    linkLabel: title
  };
}

function dashboardBarCard_(title, subtitle, counts, asOf) {
  return dashboardBarCardFromRows_(title, subtitle, dashboardTopRows_(counts, 12), asOf);
}

function dashboardBarCardFromRows_(title, subtitle, rows, asOf) {
  return {
    key: dashboardCardKey_(title),
    title: title,
    subtitle: subtitle,
    type: "bar",
    rows: rows || [],
    asOf: asOf,
    linkLabel: title
  };
}

function dashboardCardKey_(title) {
  return String(title || "").toLowerCase().replace(/[^a-z0-9]+/g, "-").replace(/^-|-$/g, "");
}

function dashboardDateRows_(counts) {
  return Object.keys(counts || {})
    .map(function(label) {
      const parsedDate = parseUsDate(label);
      return {
        label: label,
        count: Number(counts[label] || 0),
        sortKey: parsedDate ? parsedDate.getTime() : 0
      };
    })
    .sort(function(first, second) {
      if (first.sortKey && second.sortKey) return first.sortKey - second.sortKey;
      return first.label.localeCompare(second.label);
    })
    .map(function(row) {
      return { label: row.label, count: row.count };
    });
}

function dashboardTopRows_(counts, limit) {
  return Object.keys(counts || {})
    .sort(function(first, second) {
      return Number(counts[second] || 0) - Number(counts[first] || 0) || first.localeCompare(second);
    })
    .slice(0, limit || 12)
    .map(function(label) {
      return { label: label, count: Number(counts[label] || 0) };
    });
}

function getDashboardReferenceDueCounts_(rangeStart, rangeEnd, tomorrow) {
  const byDate = {};
  const tomorrowByCreditor = {};
  const cacheKey = "dash-ref:"
    + Utilities.formatDate(rangeStart, Session.getScriptTimeZone(), "yyyyMMdd")
    + ":"
    + Utilities.formatDate(rangeEnd, Session.getScriptTimeZone(), "yyyyMMdd")
    + ":"
    + Utilities.formatDate(tomorrow, Session.getScriptTimeZone(), "yyyyMMdd");
  try {
    const cached = CacheService.getScriptCache().get(cacheKey);
    if (cached) return JSON.parse(cached);
  } catch (error) {
    // Continue without cache.
  }

  try {
    const referenceSheet = getClientReferenceSheet_(getClientReferenceSpreadsheet_());
    if (!referenceSheet || referenceSheet.getLastRow() < 2) {
      return { byDate: byDate, tomorrowByCreditor: tomorrowByCreditor };
    }

    const headers = referenceSheet.getRange(1, 1, 1, referenceSheet.getLastColumn()).getValues()[0].map(String);
    const dueColumn = getHeaderColumn(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New", "Due Date"]);
    const creditorColumn = getHeaderColumn(headers, ["CREDITOR_NAME", "Creditor Name", "Creditor"]);
    if (!dueColumn) return { byDate: byDate, tomorrowByCreditor: tomorrowByCreditor };

    const values = referenceSheet.getRange(2, 1, referenceSheet.getLastRow() - 1, referenceSheet.getLastColumn()).getValues();
    values.forEach(function(row) {
      const dueDate = parseUsDate(normalizeUsDate(row[dueColumn - 1]));
      if (!dueDate) return;
      const creditor = creditorColumn ? String(row[creditorColumn - 1] || "Blank creditor").trim() || "Blank creditor" : "Blank creditor";
      if (dueDate >= rangeStart && dueDate <= rangeEnd) {
        incrementDashboardCount_(byDate, formatUsDate(dueDate));
      }
      if (isSameDashboardDate_(dueDate, tomorrow)) {
        incrementDashboardCount_(tomorrowByCreditor, creditor);
      }
    });
  } catch (error) {
    return { byDate: byDate, tomorrowByCreditor: tomorrowByCreditor };
  }

  const result = { byDate: byDate, tomorrowByCreditor: tomorrowByCreditor };
  try {
    CacheService.getScriptCache().put(cacheKey, JSON.stringify(result), 900);
  } catch (error) {
    // Cache is only a speed helper.
  }
  return result;
}

function incrementDashboardCount_(counts, key) {
  const label = String(key || "Blank").trim() || "Blank";
  counts[label] = Number(counts[label] || 0) + 1;
}

function dashboardValue_(row, column) {
  return column ? String(row[column - 1] == null ? "" : formatSheetCell(row[column - 1])).trim() : "";
}

function isDashboardCompleted_(status) {
  const normalized = String(status || "").trim().toLowerCase();
  return normalized === "payment setup completed" || normalized === "bulk payments setup successfully";
}

function isSameDashboardDate_(first, second) {
  return Boolean(first && second
    && first.getFullYear() === second.getFullYear()
    && first.getMonth() === second.getMonth()
    && first.getDate() === second.getDate());
}

function dashboardSetupMode_(comments) {
  return String(comments || "").toLowerCase().indexOf("web") !== -1 ? "Web" : "CBP";
}

function dashboardFollowupWindowEnd_(today) {
  const end = new Date(today);
  if (today.getDay() === 5) end.setDate(end.getDate() + 2);
  if (today.getDay() === 6) end.setDate(end.getDate() + 1);
  return end;
}

function dashboardFollowupSubtitle_(today, followupEnd) {
  if (isSameDashboardDate_(today, followupEnd)) return "By creditor";
  return "By creditor, including weekend";
}

function getDashboardAssignmentSummary_(today, monthStart) {
  const statusCounts = {};
  const agentCounts = {};
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(AGENT_ASSIGNMENT_SHEET_NAME);
  if (!sheet || sheet.getLastRow() < 2) return { statusCounts: statusCounts, agentCounts: agentCounts };

  const values = sheet.getRange(1, 1, sheet.getLastRow(), sheet.getLastColumn()).getValues();
  const headers = values[0].map(String);
  const assignedAtColumn = headers.indexOf("Assigned At") + 1;
  const agentColumn = headers.indexOf("Assigned To Name") + 1;
  const statusColumn = headers.indexOf("Status") + 1;

  values.slice(1).forEach(function(row) {
    const assignedAt = parseUsDate(normalizeUsDate(dashboardValue_(row, assignedAtColumn)));
    if (assignedAt && assignedAt < monthStart) return;
    const status = dashboardValue_(row, statusColumn) || "Open";
    const agent = dashboardValue_(row, agentColumn) || "Unassigned";
    incrementDashboardCount_(statusCounts, status);
    incrementDashboardCount_(agentCounts, agent);
  });

  return { statusCounts: statusCounts, agentCounts: agentCounts };
}

function getAgentWorkedReportData_(startDate, endDate) {
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME);
  if (!sheet || sheet.getLastRow() < 2) return { headers: [], rows: [], rawRows: [], workedDateColumn: 0, agentColumn: 0 };

  const values = sheet.getRange(1, 1, sheet.getLastRow(), sheet.getLastColumn()).getValues();
  const headers = values[0].map(String);
  const workedDateColumn = getHeaderColumn(headers, ["Received on", "CFT Team Payment Worked date", "Payment Received on (Date)", "Received on Date", "Received on (Date)"]);
  const agentColumn = getHeaderColumn(headers, ["USER", "Agent Name"]);
  const followupColumn = getHeaderColumn(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]);
  const outcomeColumn = getHeaderColumn(headers, ["PAYMENT_STATUS", "Payment Outcome"]);
  if (!workedDateColumn) throw new Error("Master sheet does not have Received on column.");
  if (!agentColumn) throw new Error("Master sheet does not have USER column.");
  if (!followupColumn) throw new Error("Master sheet does not have Follow up Date column.");

  const rangeStart = parseUsDate(startDate);
  const rangeEnd = parseUsDate(endDate);
  if (!rangeStart || !rangeEnd) throw new Error("Choose a valid worked date range.");

  const rawRows = values.slice(1).filter(function(row) {
    const workedDate = parseUsDate(normalizeUsDate(row[workedDateColumn - 1]));
    const followupDate = String(row[followupColumn - 1] || "").trim().toUpperCase();
    const outcome = outcomeColumn ? String(row[outcomeColumn - 1] || "").trim().toUpperCase() : "";
    const completedOutcome = !outcome || outcome === "PAYMENT SETUP COMPLETED" || outcome === "BULK PAYMENTS SETUP SUCCESSFULLY";
    return workedDate && workedDate >= rangeStart && workedDate <= rangeEnd && followupDate === "N/A" && completedOutcome;
  }).sort(function(first, second) {
    const firstDate = normalizeUsDate(first[workedDateColumn - 1]);
    const secondDate = normalizeUsDate(second[workedDateColumn - 1]);
    const firstAgent = String(first[agentColumn - 1] || "");
    const secondAgent = String(second[agentColumn - 1] || "");
    return firstDate.localeCompare(secondDate) || firstAgent.localeCompare(secondAgent);
  });

  return {
    headers: headers,
    rows: rawRows.map(function(row) { return row.map(formatSheetCell); }),
    rawRows: rawRows,
    workedDateColumn: workedDateColumn,
    agentColumn: agentColumn
  };
}

function getNewPaymentRows(sourceSpreadsheetUrl, sourceSheetName) {
  requireCrmAccess();
  const sourceId = extractSpreadsheetId(sourceSpreadsheetUrl);
  if (!sourceId) throw new Error("Daily sheet URL is not valid.");

  const referenceSheet = getClientReferenceSheet_(getClientReferenceSpreadsheet_());
  const sourceSpreadsheet = SpreadsheetApp.openById(sourceId);
  return getNewPaymentRowsFromSpreadsheet_(referenceSheet, sourceSpreadsheet, sourceSheetName);
}

function getNewPaymentRowsFromRows(sourceValues) {
  requireCrmAccess();
  const referenceSheet = getClientReferenceSheet_(getClientReferenceSpreadsheet_());
  return getNewPaymentRowsFromValues_(referenceSheet, sourceValues || []);
}

function getNewPaymentRowsFromSpreadsheet_(referenceSheet, sourceSpreadsheet, sourceSheetName) {
  const sourceSheet = sourceSheetName
    ? sourceSpreadsheet.getSheetByName(sourceSheetName)
    : sourceSpreadsheet.getSheets()[0];
  if (!referenceSheet) throw new Error("Client reference sheet was not found.");
  if (!sourceSheet) throw new Error("Daily sheet tab was not found.");

  const sourceValues = sourceSheet.getDataRange().getValues();
  return getNewPaymentRowsFromValues_(referenceSheet, sourceValues);
}

function getNewPaymentRowsFromValues_(referenceSheet, sourceValues) {
  if (!referenceSheet) throw new Error("Client reference sheet was not found.");
  if (sourceValues.length < 2) return { headers: [], rows: [] };

  const referenceHeaders = referenceSheet.getRange(1, 1, 1, referenceSheet.getLastColumn()).getDisplayValues()[0].map(String);
  const referenceScheduleColumn = getScheduleIdColumn(referenceHeaders);
  if (!referenceScheduleColumn) throw new Error("Client reference sheet must have a CRM Payment Schedule ID column.");
  const existingReferenceIds = getExistingReferenceScheduleIds_(referenceSheet, referenceScheduleColumn);
  const headers = sourceValues[0].map(String);
  const scheduleColumn = getScheduleIdColumn(headers);
  if (!scheduleColumn) throw new Error("Daily sheet must have a CRM Payment Schedule ID column. Current headers: " + headers.join(", "));

  const outputHeaders = headers.concat(["Reference Match Status"]);
  const rows = sourceValues.slice(1).filter(function(row) {
    const scheduleId = String(row[scheduleColumn - 1] || "").trim();
    return scheduleId && !existingReferenceIds.has(scheduleId.toLowerCase());
  }).map(function(row) {
    return row.map(formatSheetCell).concat(["N/A"]);
  });

  return { headers: outputHeaders, rows: rows };
}

function getAssignableFollowupWorkItems(selection) {
  requireCrmAdminAccess();
  const report = getFollowupRowsBySelection(selection || {});
  const allItems = mapRowsToWorkItems_(report.headers, report.rows, "Follow-up");
  const activeAssignmentIds = getActiveAssignmentScheduleIds_();
  const items = allItems.filter(function(item) {
    const scheduleId = String(item.crmPaymentScheduleId || "").trim().toLowerCase();
    return !scheduleId || !activeAssignmentIds.has(scheduleId);
  });
  return {
    headers: report.headers,
    items: items.slice(0, 500),
    summary: addCreditorSummaryToWorkSummary_(
      buildWorkAssignmentSummary_("Follow-up", selection || {}, allItems.length),
      allItems
    )
  };
}

function getAssignableNewCaseWorkItemsFromRows(sourceValues) {
  requireCrmAdminAccess();
  const referenceSheet = getClientReferenceSheet_(getClientReferenceSpreadsheet_());
  const report = getNewPaymentRowsFromValues_(referenceSheet, sourceValues || []);
  return {
    headers: report.headers,
    items: mapRowsToWorkItems_(report.headers, report.rows, "New Case").slice(0, 500)
  };
}

function getAssignableNewCaseWorkItemsFromReference(selection) {
  requireCrmAdminAccess();
  const referenceSheet = getClientReferenceSheet_(getClientReferenceSpreadsheet_());
  if (!referenceSheet || referenceSheet.getLastRow() < 2) return { headers: [], items: [] };

  const headers = referenceSheet.getRange(1, 1, 1, referenceSheet.getLastColumn()).getDisplayValues()[0].map(String);
  const scheduleColumn = getScheduleIdColumn(headers);
  if (!scheduleColumn) throw new Error("Client reference sheet must have a CRM Payment Schedule ID column.");
  const paymentDueColumn = getHeaderColumn(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New", "Due Date"]);
  if (!paymentDueColumn) throw new Error("Client reference sheet must have PAYMENT_SCHEDULE_DATE for New Case assignment.");

  const rangeStart = selection && selection.startDate ? parseUsDate(selection.startDate) : null;
  const rangeEnd = selection && selection.endDate ? parseUsDate(selection.endDate) : null;
  if (!rangeStart || !rangeEnd) throw new Error("Choose a valid payment due date range for New Cases.");

  const existingMasterIds = getExistingMasterScheduleIds_();
  const activeAssignmentIds = getActiveAssignmentScheduleIds_();
  const outputRows = [];
  const creditorCounts = {};
  let dueTotal = 0;
  const maxItems = 500;
  const chunkSize = 2000;
  const lastRow = referenceSheet.getLastRow();
  const lastColumn = referenceSheet.getLastColumn();
  const creditorColumn = getHeaderColumn(headers, ["CREDITOR_NAME", "Creditor Name", "Creditor"]);

  for (let startRow = 2; startRow <= lastRow; startRow += chunkSize) {
    const rowCount = Math.min(chunkSize, lastRow - startRow + 1);
    const rows = referenceSheet.getRange(startRow, 1, rowCount, lastColumn).getDisplayValues();
    rows.forEach(function(row) {
      const scheduleId = String(row[scheduleColumn - 1] || "").trim().toLowerCase();
      if (!scheduleId) return;
      const paymentDueDate = parseUsDate(normalizeUsDate(row[paymentDueColumn - 1]));
      if (!paymentDueDate || paymentDueDate < rangeStart || paymentDueDate > rangeEnd) return;
      if (existingMasterIds.has(scheduleId)) return;
      dueTotal += 1;
      const creditorName = creditorColumn ? String(row[creditorColumn - 1] || "Blank creditor").trim() || "Blank creditor" : "Blank creditor";
      creditorCounts[creditorName] = (creditorCounts[creditorName] || 0) + 1;
      if (outputRows.length >= maxItems) return;
      if (activeAssignmentIds.has(scheduleId)) return;
      outputRows.push(row.map(formatSheetCell));
    });
  }

  return {
    headers: headers,
    items: mapRowsToWorkItems_(headers, outputRows, "New Case"),
    summary: addCreditorSummaryToWorkSummary_(
      buildWorkAssignmentSummary_("New Case", selection || {}, dueTotal),
      null,
      creditorCounts
    )
  };
}

function addCreditorSummaryToWorkSummary_(summary, items, creditorCounts) {
  const counts = creditorCounts || {};
  if (!creditorCounts) {
    (items || []).forEach(function(item) {
      const creditorName = String(item.creditorName || "Blank creditor").trim() || "Blank creditor";
      counts[creditorName] = (counts[creditorName] || 0) + 1;
    });
  }
  summary.byCreditor = Object.keys(counts)
    .sort(function(first, second) {
      return counts[second] - counts[first] || first.localeCompare(second);
    })
    .map(function(name) {
      return { name: name, count: counts[name] };
    });
  return summary;
}

function buildWorkAssignmentSummary_(source, selection, dueTotal) {
  const summary = {
    dueTotal: Number(dueTotal || 0),
    assignedTotal: 0,
    completedTotal: 0,
    remainingTotal: Number(dueTotal || 0),
    byAgent: []
  };

  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(AGENT_ASSIGNMENT_SHEET_NAME);
  if (!sheet || sheet.getLastRow() < 2) return summary;

  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const values = sheet.getRange(2, 1, sheet.getLastRow() - 1, headers.length).getDisplayValues();
  const sourceColumn = headers.indexOf("Source") + 1;
  const agentColumn = headers.indexOf("Assigned To Name") + 1;
  const statusColumn = headers.indexOf("Status") + 1;
  const followupColumn = headers.indexOf("Follow up Date") + 1;
  const dueColumn = headers.indexOf("Payment Due Date") + 1;
  const rangeStart = selection && selection.startDate ? parseUsDate(selection.startDate) : null;
  const rangeEnd = selection && selection.endDate ? parseUsDate(selection.endDate) : null;
  const hasRange = Boolean(rangeStart && rangeEnd);
  const agentMap = {};

  values.forEach(function(row) {
    if (sourceColumn && source && String(row[sourceColumn - 1] || "") !== source) return;
    if (hasRange) {
      const dateValue = source === "Follow-up"
        ? String(row[(followupColumn || dueColumn) - 1] || "")
        : String(row[(dueColumn || followupColumn) - 1] || "");
      const parsedDate = parseUsDate(normalizeUsDate(dateValue));
      if (!parsedDate || parsedDate < rangeStart || parsedDate > rangeEnd) return;
    }

    const agentName = agentColumn ? String(row[agentColumn - 1] || "Unassigned").trim() || "Unassigned" : "Unassigned";
    const status = statusColumn ? String(row[statusColumn - 1] || "").trim() : "";
    if (!agentMap[agentName]) agentMap[agentName] = { name: agentName, assigned: 0, completed: 0, remaining: 0 };
    agentMap[agentName].assigned += 1;
    summary.assignedTotal += 1;
    if (status === "Completed") {
      agentMap[agentName].completed += 1;
      summary.completedTotal += 1;
    } else {
      agentMap[agentName].remaining += 1;
    }
  });

  summary.remainingTotal = Math.max(0, summary.dueTotal - summary.assignedTotal);
  summary.byAgent = Object.keys(agentMap).sort().map(function(agentName) {
    return agentMap[agentName];
  });
  return summary;
}

function getExistingMasterScheduleIds_() {
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(SHEET_NAME);
  if (!sheet || sheet.getLastRow() < 2) return new Set();
  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const scheduleColumn = getScheduleIdColumn(headers);
  if (!scheduleColumn) return new Set();
  const values = sheet.getRange(2, scheduleColumn, sheet.getLastRow() - 1, 1).getDisplayValues();
  const ids = new Set();
  values.forEach(function(row) {
    const scheduleId = String(row[0] || "").trim().toLowerCase();
    if (scheduleId) ids.add(scheduleId);
  });
  return ids;
}

function getActiveAssignmentScheduleIds_() {
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(AGENT_ASSIGNMENT_SHEET_NAME);
  if (!sheet || sheet.getLastRow() < 2) return new Set();
  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const scheduleColumn = headers.indexOf("CRM Payment Schedule ID") + 1;
  const statusColumn = headers.indexOf("Status") + 1;
  if (!scheduleColumn) return new Set();
  const values = sheet.getRange(2, 1, sheet.getLastRow() - 1, sheet.getLastColumn()).getDisplayValues();
  const ids = new Set();
  values.forEach(function(row) {
    const status = statusColumn ? String(row[statusColumn - 1] || "").trim().toLowerCase() : "";
    if (status === "completed" || status === "cancelled" || status === "canceled") return;
    const scheduleId = String(row[scheduleColumn - 1] || "").trim().toLowerCase();
    if (scheduleId) ids.add(scheduleId);
  });
  return ids;
}

function mapRowsToWorkItems_(headers, rows, source) {
  const columns = {
    clientId: getHeaderColumn(headers, ["ENROLLMENT_EXTERNAL_ID", "Client ID", "Client Id"]),
    clientFullName: getHeaderColumn(headers, ["CLIENT_FULL_NAME", "Client Full Name", "Client Name"]),
    scheduleId: getHeaderColumn(headers, ["CRM_PAYMENT_SCHEDULE_ID", "CRM Payment Schedule ID", "DM Payment Schedule ID", "Schedule ID"]),
    paymentDueDate: getHeaderColumn(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New", "Due Date"]),
    paymentAmount: getHeaderColumn(headers, ["PAYMENT_AMOUNT", "Payment Amount", "Amount"]),
    creditorName: getHeaderColumn(headers, ["CREDITOR_NAME", "Creditor Name", "Creditor"]),
    debtAccount: getHeaderColumn(headers, ["DEBT_ACCOUNT_NUMBER", "Current Account Numbers", "Current Account Number", "Account Number"]),
    originalAccount: getHeaderColumn(headers, ["ORIGINAL_ACCOUNT_NUMBER", "Original Account Number", "Original Account Numbers"]),
    followupDate: getHeaderColumn(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]),
    comments: getHeaderColumn(headers, ["Comments", "Comment", "Notes"])
  };

  return (rows || []).map(function(row) {
    return {
      source: source || "",
      clientId: getWorkItemCell_(row, columns.clientId),
      clientFullName: getWorkItemCell_(row, columns.clientFullName),
      crmPaymentScheduleId: getWorkItemCell_(row, columns.scheduleId),
      paymentDueDate: normalizeUsDate(getWorkItemCell_(row, columns.paymentDueDate)) || getWorkItemCell_(row, columns.paymentDueDate),
      paymentAmount: getWorkItemCell_(row, columns.paymentAmount),
      creditorName: getWorkItemCell_(row, columns.creditorName),
      debtAccountNumber: formatAccountNumberForSheet_(getWorkItemCell_(row, columns.debtAccount)),
      originalAccountNumber: formatAccountNumberForSheet_(getWorkItemCell_(row, columns.originalAccount)),
      followupDate: normalizeUsDate(getWorkItemCell_(row, columns.followupDate)) || getWorkItemCell_(row, columns.followupDate),
      comments: getWorkItemCell_(row, columns.comments)
    };
  }).filter(function(item) {
    return item.clientId || item.crmPaymentScheduleId;
  });
}

function getWorkItemCell_(row, column) {
  return column ? String(row[column - 1] || "").trim() : "";
}

function getAgentAssignmentsSheet_() {
  const ss = getTargetSpreadsheet();
  const sheet = ss.getSheetByName(AGENT_ASSIGNMENT_SHEET_NAME) || ss.insertSheet(AGENT_ASSIGNMENT_SHEET_NAME);
  ensureHeaders(sheet, AGENT_ASSIGNMENT_HEADERS);
  return sheet;
}

function saveAgentAssignments(items, assignedEmail) {
  requireCrmAdminAccess();
  const normalizedEmail = normalizeEmail(assignedEmail);
  if (ALLOWED_CRM_USERS.indexOf(normalizedEmail) === -1) {
    throw new Error("Choose an approved CRM agent before assigning work.");
  }
  const assignedProfile = getCrmUserProfile_(normalizedEmail);
  const sheet = getAgentAssignmentsSheet_();
  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const assignedAt = new Date();
  const assignedBy = getCurrentUserEmail();
  const rows = (Array.isArray(items) ? items : []).map(function(item) {
    const row = new Array(headers.length).fill("");
    setAssignmentRowValue_(row, headers, "Assignment ID", Utilities.getUuid());
    setAssignmentRowValue_(row, headers, "Source", item.source || "");
    setAssignmentRowValue_(row, headers, "Assigned To Email", normalizedEmail);
    setAssignmentRowValue_(row, headers, "Assigned To Name", assignedProfile.name);
    setAssignmentRowValue_(row, headers, "Status", "Open");
    setAssignmentRowValue_(row, headers, "Assigned At", assignedAt);
    setAssignmentRowValue_(row, headers, "Assigned By", assignedBy);
    setAssignmentRowValue_(row, headers, "Client ID", item.clientId || "");
    setAssignmentRowValue_(row, headers, "Client Full Name", item.clientFullName || "");
    setAssignmentRowValue_(row, headers, "CRM Payment Schedule ID", item.crmPaymentScheduleId || "");
    setAssignmentRowValue_(row, headers, "Payment Due Date", normalizeUsDate(item.paymentDueDate) || item.paymentDueDate || "");
    setAssignmentRowValue_(row, headers, "Payment Amount", item.paymentAmount || "");
    setAssignmentRowValue_(row, headers, "Creditor Name", item.creditorName || "");
    setAssignmentRowValue_(row, headers, "DEBT_ACCOUNT_NUMBER", item.debtAccountNumber || "");
    setAssignmentRowValue_(row, headers, "ORIGINAL_ACCOUNT_NUMBER", item.originalAccountNumber || "");
    setAssignmentRowValue_(row, headers, "Follow up Date", normalizeUsDate(item.followupDate) || item.followupDate || "");
    setAssignmentRowValue_(row, headers, "Comments", item.comments || "");
    return row;
  });

  if (!rows.length) throw new Error("Select at least one case to assign.");
  sheet.getRange(sheet.getLastRow() + 1, 1, rows.length, headers.length).setValues(rows);
  return {
    ok: true,
    assigned: rows.length,
    assignedTo: assignedProfile.name,
    assignedAt: assignedAt.toISOString()
  };
}

function setAssignmentRowValue_(row, headers, header, value) {
  const index = headers.indexOf(header);
  if (index >= 0) row[index] = value;
}

function getMyWorkQueue(status, source) {
  requireCrmAccess();
  const sheet = getAgentAssignmentsSheet_();
  if (sheet.getLastRow() < 2) return { items: [], summary: buildMyWorkQueueSummary_([], source || "Follow-up") };
  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const values = sheet.getRange(2, 1, sheet.getLastRow() - 1, headers.length).getDisplayValues();
  const email = getCurrentUserEmail();
  const isAdmin = CRM_ADMIN_USERS.indexOf(email) !== -1;
  const selectedStatus = String(status || "Open").trim();
  const selectedSource = String(source || "Follow-up").trim();
  const baseItems = values.map(function(row, index) {
    const item = assignmentRowToObject_(headers, row);
    item.rowNumber = index + 2;
    return item;
  }).filter(function(item) {
    if (!isAdmin && String(item.assignedToEmail || "").toLowerCase() !== email) return false;
    return true;
  }).filter(function(item) {
    return isCurrentMonthDate_(item.paymentDueDate);
  });
  const items = baseItems.filter(function(item) {
    if (selectedSource && String(item.source || "") !== selectedSource) return false;
    if (!selectedStatus || selectedStatus === "All") return true;
    return String(item.status || "") === selectedStatus;
  });
  return {
    items: items,
    summary: buildMyWorkQueueSummary_(baseItems, selectedSource)
  };
}

function buildMyWorkQueueSummary_(items, selectedSource) {
  const now = new Date();
  const today = new Date(now.getFullYear(), now.getMonth(), now.getDate());
  const summary = {
    followupAssigned: 0,
    newAssigned: 0,
    sameDayPayments: 0,
    completed: 0,
    remaining: 0,
    byCreditor: []
  };
  const creditorCounts = {};
  (items || []).forEach(function(item) {
    const source = String(item.source || "");
    const status = String(item.status || "");
    const completed = status === "Completed";
    if (source === "Follow-up") summary.followupAssigned += 1;
    if (source === "New Case") summary.newAssigned += 1;
    if (selectedSource && source !== selectedSource) return;
    if (completed) {
      summary.completed += 1;
      return;
    }
    summary.remaining += 1;
    const dueDate = parseUsDate(normalizeUsDate(item.paymentDueDate));
    if (isSameDashboardDate_(dueDate, today)) summary.sameDayPayments += 1;
    const creditorName = String(item.creditorName || "Blank creditor").trim() || "Blank creditor";
    creditorCounts[creditorName] = (creditorCounts[creditorName] || 0) + 1;
  });
  summary.byCreditor = Object.keys(creditorCounts)
    .sort(function(first, second) {
      return creditorCounts[second] - creditorCounts[first] || first.localeCompare(second);
    })
    .map(function(name) {
      return { name: name, count: creditorCounts[name] };
    });
  return summary;
}

function getMyWorkQueueReminderSummary() {
  requireCrmAccess();
  const sheet = getAgentAssignmentsSheet_();
  const summary = {
    followupRemaining: 0,
    newRemaining: 0,
    totalRemaining: 0,
    byCreditor: []
  };
  if (sheet.getLastRow() < 2) return summary;

  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const values = sheet.getRange(2, 1, sheet.getLastRow() - 1, headers.length).getDisplayValues();
  const email = getCurrentUserEmail();
  const creditorCounts = {};

  values.forEach(function(row) {
    const item = assignmentRowToObject_(headers, row);
    if (String(item.assignedToEmail || "").toLowerCase() !== email) return;
    if (!isCurrentMonthDate_(item.paymentDueDate)) return;
    const status = String(item.status || "");
    if (status === "Completed" || status === "Removed" || status === "Cancelled") return;

    if (String(item.source || "") === "Follow-up") summary.followupRemaining += 1;
    if (String(item.source || "") === "New Case") summary.newRemaining += 1;
    const creditorName = String(item.creditorName || "Blank creditor").trim() || "Blank creditor";
    creditorCounts[creditorName] = (creditorCounts[creditorName] || 0) + 1;
  });

  summary.totalRemaining = summary.followupRemaining + summary.newRemaining;
  summary.byCreditor = Object.keys(creditorCounts)
    .sort(function(first, second) {
      return creditorCounts[second] - creditorCounts[first] || first.localeCompare(second);
    })
    .map(function(name) {
      return { name: name, count: creditorCounts[name] };
    });
  return summary;
}

function isCurrentMonthDate_(value) {
  const date = parseUsDate(normalizeUsDate(value));
  if (!date) return false;
  const now = new Date();
  return date.getFullYear() === now.getFullYear() && date.getMonth() === now.getMonth();
}

function assignmentRowToObject_(headers, row) {
  function value(header) {
    const index = headers.indexOf(header);
    return index >= 0 ? String(row[index] || "").trim() : "";
  }
  return {
    assignmentId: value("Assignment ID"),
    source: value("Source"),
    assignedToEmail: value("Assigned To Email"),
    assignedToName: value("Assigned To Name"),
    status: value("Status"),
    assignedAt: value("Assigned At"),
    clientId: value("Client ID"),
    clientFullName: value("Client Full Name"),
    crmPaymentScheduleId: value("CRM Payment Schedule ID"),
    paymentDueDate: value("Payment Due Date"),
    paymentAmount: value("Payment Amount"),
    creditorName: value("Creditor Name"),
    debtAccountNumber: value("DEBT_ACCOUNT_NUMBER"),
    originalAccountNumber: value("ORIGINAL_ACCOUNT_NUMBER"),
    followupDate: value("Follow up Date"),
    comments: value("Comments")
  };
}

function updateAgentAssignmentStatus(assignmentId, status) {
  requireCrmAccess();
  const sheet = getAgentAssignmentsSheet_();
  if (sheet.getLastRow() < 2) throw new Error("No assignment rows found.");
  const headers = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getDisplayValues()[0].map(String);
  const assignmentColumn = headers.indexOf("Assignment ID") + 1;
  const assignedEmailColumn = headers.indexOf("Assigned To Email") + 1;
  const statusColumn = headers.indexOf("Status") + 1;
  const openedAtColumn = headers.indexOf("Opened At") + 1;
  const completedAtColumn = headers.indexOf("Completed At") + 1;
  if (!assignmentColumn || !statusColumn) throw new Error("Assignment sheet headers are incomplete.");

  const finder = sheet.getRange(2, assignmentColumn, sheet.getLastRow() - 1, 1)
    .createTextFinder(String(assignmentId || ""))
    .matchEntireCell(true)
    .matchCase(false);
  const cell = finder.findNext();
  if (!cell) throw new Error("Assignment was not found.");
  const rowNumber = cell.getRow();
  const assignedEmail = assignedEmailColumn ? normalizeEmail(sheet.getRange(rowNumber, assignedEmailColumn).getDisplayValue()) : "";
  if (!isCrmAdmin() && assignedEmail !== getCurrentUserEmail()) {
    throw new Error("You can update only your own assigned cases.");
  }
  sheet.getRange(rowNumber, statusColumn).setValue(status || "Open");
  if (status === "In Progress" && openedAtColumn) sheet.getRange(rowNumber, openedAtColumn).setValue(new Date());
  if (status === "Completed" && completedAtColumn) sheet.getRange(rowNumber, completedAtColumn).setValue(new Date());
  return { ok: true, assignmentId: assignmentId, status: status };
}

function importNewClientReferenceRows(sourceSpreadsheetUrl, sourceSheetName) {
  requireCrmAdminAccess();
  const sourceId = extractSpreadsheetId(sourceSpreadsheetUrl);
  if (!sourceId) throw new Error("Daily sheet URL is not valid.");

  const sourceSpreadsheet = SpreadsheetApp.openById(sourceId);
  const sourceSheet = sourceSheetName
    ? sourceSpreadsheet.getSheetByName(sourceSheetName)
    : sourceSpreadsheet.getSheets()[0];
  if (!sourceSheet) throw new Error("Daily sheet tab was not found.");

  const sourceValues = sourceSheet.getDataRange().getValues();
  return importNewClientReferenceRowsFromValues_(sourceValues, sourceSpreadsheet.getName());
}

function importNewClientReferenceRowsFromRows(sourceValues) {
  requireCrmAdminAccess();
  return importNewClientReferenceRowsFromValues_(sourceValues || [], "Uploaded Daily Excel");
}

function importNewClientReferenceRowsFromValues_(sourceValues, sourceName) {
  return runWithClientReferenceLock_(function() {
    const values = (sourceValues || []).filter(function(row) {
      return row && row.some(function(value) { return String(value || "").trim(); });
    });
    if (values.length < 2) {
      throw new Error("The daily report does not have data rows.");
    }

    const sourceHeaders = values[0].map(function(header) { return String(header || "").trim(); });
    const sourceScheduleColumn = getScheduleIdColumn(sourceHeaders);
    if (!sourceScheduleColumn) {
      throw new Error("Daily report must have a CRM Payment Schedule ID column. Current headers: " + sourceHeaders.join(", "));
    }

    const referenceSpreadsheet = getClientReferenceSpreadsheet_();
    let referenceSheet = referenceSpreadsheet.getSheetByName(CLIENT_REFERENCE_SHEET_NAME);
    if (!referenceSheet) referenceSheet = referenceSpreadsheet.insertSheet(CLIENT_REFERENCE_SHEET_NAME);

    const referenceHeaders = ensureClientReferenceHeaders_(referenceSheet, sourceHeaders);
    formatClientReferenceTextColumns_(referenceSheet, referenceHeaders);
    const referenceScheduleColumn = getScheduleIdColumn(referenceHeaders);
    if (!referenceScheduleColumn) {
      throw new Error("Client reference sheet is missing CRM_PAYMENT_SCHEDULE_ID column.");
    }

    const existingIds = getExistingReferenceScheduleIds_(referenceSheet, referenceScheduleColumn);
    const sourceHeaderMap = buildNormalizedHeaderMap_(sourceHeaders);
    const seenUploadIds = {};
    const rowsToAppend = [];
    const rowsToAppendScheduleIds = [];
    let skippedExisting = 0;
    let skippedDuplicateUpload = 0;
    let skippedBlankSchedule = 0;

    values.slice(1).forEach(function(sourceRow) {
      const scheduleId = cleanReferenceTextCell_(sourceRow[sourceScheduleColumn - 1]);
      const scheduleKey = scheduleId.toLowerCase();
      if (!scheduleId) {
        skippedBlankSchedule += 1;
        return;
      }
      if (seenUploadIds[scheduleKey]) {
        skippedDuplicateUpload += 1;
        return;
      }
      seenUploadIds[scheduleKey] = true;
      if (existingIds.has(scheduleKey)) {
        skippedExisting += 1;
        return;
      }

      rowsToAppend.push(referenceHeaders.map(function(header) {
        const sourceIndex = sourceHeaderMap[normalizeBulkHeader_(header)];
        const value = sourceIndex === undefined ? "" : sourceRow[sourceIndex];
        return formatClientReferenceImportValue_(header, value);
      }));
      rowsToAppendScheduleIds.push(scheduleKey);
    });

    let appendedStartRow = 0;
    if (rowsToAppend.length) {
      appendedStartRow = referenceSheet.getLastRow() + 1;
      for (let start = 0; start < rowsToAppend.length; start += 5000) {
        const chunk = rowsToAppend.slice(start, start + 5000);
        referenceSheet.getRange(appendedStartRow + start, 1, chunk.length, referenceHeaders.length).setValues(chunk);
      }
      SpreadsheetApp.flush();
    }

    const verificationResult = verifyImportedReferenceScheduleIds_(
      referenceSheet,
      referenceScheduleColumn,
      rowsToAppendScheduleIds,
      appendedStartRow
    );
    if (verificationResult.missingCount) {
      throw new Error(
        "Import verification failed: " +
        verificationResult.missingCount +
        " new CRM Payment Schedule ID(s) were not found in the reference sheet after import. Missing sample: " +
        verificationResult.missingSample.join(", ")
      );
    }

    const indexResult = updateClientReferenceIndexForImportedRows_(referenceSpreadsheet, referenceSheet, referenceHeaders, rowsToAppend, appendedStartRow);
    logClientReferenceImport_(referenceSpreadsheet, {
      sourceName: sourceName || "",
      imported: rowsToAppend.length,
      verifiedImported: verificationResult.verifiedCount,
      skippedExisting: skippedExisting,
      skippedDuplicateUpload: skippedDuplicateUpload,
      skippedBlankSchedule: skippedBlankSchedule,
      indexResult: indexResult
    });

    return {
      ok: true,
      sourceName: sourceName || "",
      imported: rowsToAppend.length,
      verifiedImported: verificationResult.verifiedCount,
      totalDailyRows: Math.max(values.length - 1, 0),
      uniqueScheduleIdsChecked: Object.keys(seenUploadIds).length,
      skippedExisting: skippedExisting,
      skippedDuplicateUpload: skippedDuplicateUpload,
      skippedBlankSchedule: skippedBlankSchedule,
      referenceSpreadsheetName: referenceSpreadsheet.getName(),
      referenceSheetName: referenceSheet.getName(),
      indexRebuilt: Boolean(indexResult && indexResult.ok),
      indexedClientCount: indexResult && indexResult.indexedClientCount || 0,
      importedAt: new Date().toISOString()
    };
  });
}

function runWithClientReferenceLock_(callback) {
  const lock = LockService.getScriptLock();
  if (!lock.tryLock(SYNC_LOCK_WAIT_MS)) {
    throw new Error("Another CRM import is running. Please try again in a minute.");
  }
  try {
    return callback();
  } finally {
    lock.releaseLock();
  }
}

function verifyImportedReferenceScheduleIds_(referenceSheet, scheduleColumn, expectedScheduleIds, appendedStartRow) {
  const expectedIds = (expectedScheduleIds || []).filter(Boolean);
  if (!expectedIds.length) {
    return { verifiedCount: 0, missingCount: 0, missingSample: [] };
  }
  if (!appendedStartRow) {
    return { verifiedCount: 0, missingCount: expectedIds.length, missingSample: expectedIds.slice(0, 10) };
  }

  const writtenValues = referenceSheet
    .getRange(appendedStartRow, scheduleColumn, expectedIds.length, 1)
    .getDisplayValues();
  const writtenIds = {};
  writtenValues.forEach(function(row) {
    const scheduleId = cleanReferenceTextCell_(row[0]).toLowerCase();
    if (scheduleId) writtenIds[scheduleId] = true;
  });

  const missing = expectedIds.filter(function(scheduleId) {
    return !writtenIds[scheduleId];
  });
  return {
    verifiedCount: expectedIds.length - missing.length,
    missingCount: missing.length,
    missingSample: missing.slice(0, 10)
  };
}

function updateClientReferenceIndexForImportedRows_(referenceSpreadsheet, referenceSheet, referenceHeaders, appendedRows, appendedStartRow) {
  if (!appendedRows.length || !appendedStartRow) {
    return {
      ok: true,
      incremental: true,
      updatedClientCount: 0,
      appendedIndexRows: 0,
      indexSheetName: CLIENT_REFERENCE_INDEX_SHEET_NAME
    };
  }

  const clientColumn = getBulkColumn_(referenceHeaders, ["ENROLLMENT_EXTERNAL_ID", "Client ID", "Client Id"]);
  if (!clientColumn) {
    return {
      ok: false,
      incremental: true,
      updatedClientCount: 0,
      appendedIndexRows: 0,
      message: "Client reference index was not updated because Client ID column was not found."
    };
  }

  let indexSheet = referenceSpreadsheet.getSheetByName(CLIENT_REFERENCE_INDEX_SHEET_NAME);
  if (!indexSheet) indexSheet = referenceSpreadsheet.insertSheet(CLIENT_REFERENCE_INDEX_SHEET_NAME);
  if (indexSheet.getLastRow() === 0) {
    indexSheet.getRange(1, 1, 1, 6).setValues([[
      "CLIENT_ID",
      "ROW_NUMBERS",
      "PAYMENT_ROW_COUNT",
      "SOURCE_SHEET",
      "SOURCE_LAST_ROW",
      "UPDATED_AT"
    ]]);
  }

  const now = new Date();
  const sourceLastRow = referenceSheet.getLastRow();
  const importedMap = {};
  appendedRows.forEach(function(row, index) {
    const clientId = normalizeLookupValue_(row[clientColumn - 1]);
    if (!clientId) return;
    if (!importedMap[clientId]) importedMap[clientId] = [];
    importedMap[clientId].push(appendedStartRow + index);
  });

  const importedClientIds = Object.keys(importedMap);
  if (!importedClientIds.length) {
    return {
      ok: true,
      incremental: true,
      updatedClientCount: 0,
      appendedIndexRows: 0,
      indexSheetName: indexSheet.getName()
    };
  }

  const lastIndexRow = indexSheet.getLastRow();
  const existingRows = lastIndexRow > 1
    ? indexSheet.getRange(2, 1, lastIndexRow - 1, 6).getDisplayValues()
    : [];
  const existingMap = {};
  existingRows.forEach(function(row, index) {
    const clientId = normalizeLookupValue_(row[0]);
    if (clientId && existingMap[clientId] === undefined) existingMap[clientId] = index;
  });

  const rowsToAppendToIndex = [];
  importedClientIds.forEach(function(clientId) {
    const importedRowNumbers = importedMap[clientId];
    const existingIndex = existingMap[clientId];
    if (existingIndex === undefined) {
      rowsToAppendToIndex.push([
        clientId,
        importedRowNumbers.join(","),
        importedRowNumbers.length,
        referenceSheet.getName(),
        sourceLastRow,
        now
      ]);
      return;
    }

    const existingRow = existingRows[existingIndex];
    const rowNumberSet = {};
    String(existingRow[1] || "")
      .split(",")
      .forEach(function(value) {
        const rowNumber = Number(String(value || "").trim());
        if (Number.isInteger(rowNumber) && rowNumber > 1) rowNumberSet[rowNumber] = true;
      });
    importedRowNumbers.forEach(function(rowNumber) {
      rowNumberSet[rowNumber] = true;
    });
    const mergedRowNumbers = Object.keys(rowNumberSet)
      .map(Number)
      .sort(function(first, second) { return first - second; });
    existingRows[existingIndex] = [
      clientId,
      mergedRowNumbers.join(","),
      mergedRowNumbers.length,
      referenceSheet.getName(),
      sourceLastRow,
      now
    ];
  });

  if (existingRows.length) {
    indexSheet.getRange(2, 1, existingRows.length, 6).setValues(existingRows);
  }
  if (rowsToAppendToIndex.length) {
    indexSheet.getRange(indexSheet.getLastRow() + 1, 1, rowsToAppendToIndex.length, 6).setValues(rowsToAppendToIndex);
  }

  try {
    indexSheet.hideSheet();
  } catch (error) {
    // Ignore if Google Sheets does not allow hiding in this context.
  }

  return {
    ok: true,
    incremental: true,
    updatedClientCount: importedClientIds.length,
    appendedIndexRows: rowsToAppendToIndex.length,
    indexSheetName: indexSheet.getName(),
    indexedClientCount: Math.max(indexSheet.getLastRow() - 1, 0),
    updatedAt: now.toISOString()
  };
}

function ensureClientReferenceHeaders_(sheet, sourceHeaders) {
  const existingLastColumn = sheet.getLastColumn();
  const existingHeaders = sheet.getLastRow() >= 1 && existingLastColumn
    ? sheet.getRange(1, 1, 1, existingLastColumn).getDisplayValues()[0].map(function(header) { return String(header || "").trim(); })
    : [];
  let headers = existingHeaders.filter(Boolean);
  if (!headers.length) headers = sourceHeaders.filter(Boolean);

  const normalized = {};
  headers.forEach(function(header) {
    normalized[normalizeBulkHeader_(header)] = true;
  });
  sourceHeaders.forEach(function(header) {
    const cleanHeader = String(header || "").trim();
    const key = normalizeBulkHeader_(cleanHeader);
    if (!cleanHeader || normalized[key]) return;
    headers.push(cleanHeader);
    normalized[key] = true;
  });

  if (!headers.length) throw new Error("Daily report header row is blank.");
  sheet.getRange(1, 1, 1, headers.length).setValues([headers]);
  return headers;
}

function formatClientReferenceTextColumns_(sheet, headers) {
  const textHeaderNames = [
    "ENROLLMENT_EXTERNAL_ID",
    "Client ID",
    "CFT_PAYMENT_SCHEDULE_ID",
    "CRM_PAYMENT_SCHEDULE_ID",
    "Creditor CFTPay ID",
    "CREDITOR_CFTPAY_ID",
    "CREDITOR_CRM_ID",
    "DEBT_ACCOUNT_NUMBER",
    "ORIGINAL_ACCOUNT_NUMBER",
    "ABA_NUMBER",
    "BANK_ACCOUNT_NUMBER",
    "ZIP_CODE",
    "Ring Central Master ID"
  ];
  headers.forEach(function(header, index) {
    if (getBulkColumn_([header], textHeaderNames)) {
      sheet.getRange(1, index + 1, Math.max(sheet.getMaxRows(), 1), 1).setNumberFormat("@");
    }
  });
}

function getExistingReferenceScheduleIds_(sheet, scheduleColumn) {
  const ids = new Set();
  if (!scheduleColumn || sheet.getLastRow() < 2) return ids;
  const values = sheet.getRange(2, scheduleColumn, sheet.getLastRow() - 1, 1).getDisplayValues();
  values.forEach(function(row) {
    const scheduleId = cleanReferenceTextCell_(row[0]).toLowerCase();
    if (scheduleId) ids.add(scheduleId);
  });
  return ids;
}

function buildNormalizedHeaderMap_(headers) {
  const map = {};
  headers.forEach(function(header, index) {
    const key = normalizeBulkHeader_(header);
    if (key && map[key] === undefined) map[key] = index;
  });
  return map;
}

function formatClientReferenceImportValue_(header, value) {
  const normalizedHeader = normalizeBulkHeader_(header);
  if (normalizedHeader === "payment schedule date"
    || normalizedHeader === "payment due date"
    || normalizedHeader === "payment due date new"
    || normalizedHeader === "received on"
    || normalizedHeader === "follow up date"
    || normalizedHeader === "cft team payment worked date") {
    return normalizeBulkDate_(formatSheetCell(value));
  }
  if (normalizedHeader === "payment amount") return normalizeBulkAmount_(formatSheetCell(value));
  if (normalizedHeader.indexOf("account") !== -1
    || normalizedHeader.indexOf("external id") !== -1
    || normalizedHeader.indexOf("schedule id") !== -1
    || normalizedHeader.indexOf("cftpay id") !== -1
    || normalizedHeader.indexOf("crm id") !== -1
    || normalizedHeader === "zip code") {
    return cleanReferenceTextCell_(value);
  }
  return formatSheetCell(value);
}

function cleanReferenceTextCell_(value) {
  return String(formatSheetCell(value) || "").trim().replace(/^[`']+/, "");
}

function logClientReferenceImport_(referenceSpreadsheet, result) {
  const logSheet = referenceSpreadsheet.getSheetByName("Client Reference Import Log")
    || referenceSpreadsheet.insertSheet("Client Reference Import Log");
  if (logSheet.getLastRow() === 0) {
    logSheet.appendRow([
      "Imported At",
      "Source",
      "Imported Rows",
      "Verified Imported Rows",
      "Skipped Existing",
      "Skipped Duplicate Upload",
      "Skipped Blank Schedule",
      "Indexed Client Count",
      "Run By"
    ]);
  }
  logSheet.appendRow([
    new Date(),
    result.sourceName || "",
    result.imported || 0,
    result.verifiedImported || 0,
    result.skippedExisting || 0,
    result.skippedDuplicateUpload || 0,
    result.skippedBlankSchedule || 0,
    result.indexResult && result.indexResult.indexedClientCount || 0,
    getCurrentUserEmail()
  ]);
}

function buildBulkPaymentPayloads_(sourceValues, dashboardOptions) {
  const options = normalizeBulkDashboardOptions_(dashboardOptions || {});
  validateBulkDashboardOptions_(options);
  const values = (sourceValues || []).filter(function(row) {
    return row && row.some(function(value) { return String(value || "").trim(); });
  });
  if (values.length < 2) return [];

  const headers = values[0].map(function(header) { return String(header || "").trim(); });
  const scheduleColumn = getBulkColumn_(headers, ["CRM_PAYMENT_SCHEDULE_ID", "CRM Payment Schedule ID", "DM Payment Schedule ID", "CRM Schedule ID", "Schedule ID"]);
  const subscriberColumn = getBulkColumn_(headers, ["COMPANY", "Subscriber"]);
  const clientIdColumn = getBulkColumn_(headers, ["ENROLLMENT_EXTERNAL_ID", "Client ID"]);
  const clientNameColumn = getBulkColumn_(headers, ["CLIENT_FULL_NAME", "Client Full Name", "Client Name"]);
  const dueDateColumn = getBulkColumn_(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date New", "Payment Due Date", "Due Date"]);
  const amountColumn = getBulkColumn_(headers, ["PAYMENT_AMOUNT", "Payment Amount", "Amount"]);
  const creditorColumn = getBulkColumn_(headers, ["CREDITOR_NAME", "Creditor Name"]);
  const contactNumberColumn = getBulkColumn_(headers, ["Cred Contact Work Number", "Cred Contact Number", "Creditor Phone Number"]);
  const accountColumn = getBulkColumn_(headers, ["DEBT_ACCOUNT_NUMBER", "Current Account Numbers", "Current Account Number", "Account Number"]);
  const emailColumn = getBulkColumn_(headers, ["Cred Email Address", "Creditor Email"]);
  const setupColumn = getBulkColumn_(headers, ["Total Payment Setup", "Payment Setup Count", "Setup Count"]);
  const commentsColumn = getBulkColumn_(headers, ["Comments", "Comment"]);
  const ringCentralColumn = getBulkColumn_(headers, ["Ring Central Master ID", "RingCentral Master ID"]);
  const outcomeColumn = getBulkColumn_(headers, ["PAYMENT_STATUS", "Payment Outcome", "Outcome"]);
  const followupRequiredColumn = getBulkColumn_(headers, ["Is Follow-up Required", "Is Followup Required", "Follow-up Required"]);
  const followupDateColumn = getBulkColumn_(headers, ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]);
  const repNameColumn = getBulkColumn_(headers, ["Rep Name", "Representative Name", "Creditor Rep Name", "Spoke With Rep", "Spoke With"]);
  const confirmationColumn = getBulkColumn_(headers, ["Conf#", "Confirmation #", "Confirmation Number", "Conf Number", "Confirmation"]);
  const escalationReasonColumn = getBulkColumn_(headers, ["Reason", "Escalation Reason", "Follow-up Reason", "Follow Up Reason"]);
  const setupFlagColumn = getBulkColumn_(headers, ["Setup Payment", "Payment Setup", "Payment Set Up", "Setup Now", "Payment Setup?", "Setup?"]);
  const masterColumnMap = getBulkMasterColumnMap_(headers);

  if (!scheduleColumn) throw new Error("Bulk upload must have CRM Payment Schedule ID or DM Payment Schedule ID column.");
  if (!subscriberColumn) throw new Error("Bulk upload must have Subscriber column.");
  if (!clientIdColumn) throw new Error("Bulk upload must have Client ID column.");
  if (!clientNameColumn) throw new Error("Bulk upload must have Client Full Name column.");
  if (!dueDateColumn) throw new Error("Bulk upload must have Payment Due Date column.");
  if (!amountColumn) throw new Error("Bulk upload must have Payment Amount column.");

  const groups = {};
  const duplicateIds = {};
  values.slice(1).forEach(function(row, index) {
    const scheduleId = getBulkCell_(row, scheduleColumn);
    if (!scheduleId) return;
    const scheduleKey = scheduleId.toLowerCase();
    if (duplicateIds[scheduleKey]) throw new Error("Duplicate CRM Payment Schedule ID in upload: " + scheduleId);
    duplicateIds[scheduleKey] = true;

    const subscriber = getBulkCell_(row, subscriberColumn).toUpperCase();
    const clientId = getBulkCell_(row, clientIdColumn);
    const clientName = getBulkCell_(row, clientNameColumn);
    if (!subscriber || !clientId || !clientName) {
      throw new Error("Row " + String(index + 2) + " is missing Subscriber, Client ID, or Client Full Name.");
    }

    const creditorName = getBulkCell_(row, creditorColumn);
    const accountNumber = cleanAccountNumber_(getBulkCell_(row, accountColumn));
    const groupKey = [subscriber, clientId, clientName, creditorName, accountNumber].join("\u0000").toLowerCase();
    const groupOptions = getBulkGroupOptions_(options, groupKey);
    if (!groups[groupKey]) {
      groups[groupKey] = {
        subscriber: subscriber,
        clientId: clientId,
        clientFullName: clientName,
        creditorName: creditorName,
        credContactWorkNumber: getBulkCell_(row, contactNumberColumn),
        currentAccountNumbers: accountNumber,
        credEmailAddress: getBulkCell_(row, emailColumn),
        totalPaymentSetup: groupOptions.totalPaymentSetup || getBulkCell_(row, setupColumn),
        comments: groupOptions.useDashboardInputs ? "" : getBulkCell_(row, commentsColumn),
        ringCentralMasterId: groupOptions.ringCentralMasterId || getBulkCell_(row, ringCentralColumn),
        paymentOutcome: groupOptions.paymentOutcome || getBulkCell_(row, outcomeColumn) || BULK_OUTCOME_COMPLETED,
        isFollowupRequired: getBulkCell_(row, followupRequiredColumn),
        followupDate: normalizeBulkDate_(getBulkCell_(row, followupDateColumn)),
        repName: groupOptions.repName || getBulkCell_(row, repNameColumn),
        confirmationNumber: groupOptions.confirmationNumber || getBulkCell_(row, confirmationColumn),
        escalationReason: groupOptions.escalationReason || getBulkCell_(row, escalationReasonColumn),
        useDashboardInputs: groupOptions.useDashboardInputs,
        rows: []
      };
    }
    fillBulkGroupValue_(groups[groupKey], "credContactWorkNumber", getBulkCell_(row, contactNumberColumn));
    fillBulkGroupValue_(groups[groupKey], "credEmailAddress", getBulkCell_(row, emailColumn));
    fillBulkGroupValue_(groups[groupKey], "totalPaymentSetup", groupOptions.totalPaymentSetup || getBulkCell_(row, setupColumn));
    if (!groupOptions.useDashboardInputs) fillBulkGroupValue_(groups[groupKey], "comments", getBulkCell_(row, commentsColumn));
    fillBulkGroupValue_(groups[groupKey], "ringCentralMasterId", groupOptions.ringCentralMasterId || getBulkCell_(row, ringCentralColumn));
    fillBulkGroupValue_(groups[groupKey], "paymentOutcome", groupOptions.paymentOutcome || getBulkCell_(row, outcomeColumn));
    fillBulkGroupValue_(groups[groupKey], "isFollowupRequired", getBulkCell_(row, followupRequiredColumn));
    fillBulkGroupValue_(groups[groupKey], "followupDate", normalizeBulkDate_(getBulkCell_(row, followupDateColumn)));
    fillBulkGroupValue_(groups[groupKey], "repName", groupOptions.repName || getBulkCell_(row, repNameColumn));
    fillBulkGroupValue_(groups[groupKey], "confirmationNumber", groupOptions.confirmationNumber || getBulkCell_(row, confirmationColumn));
    fillBulkGroupValue_(groups[groupKey], "escalationReason", groupOptions.escalationReason || getBulkCell_(row, escalationReasonColumn));

    groups[groupKey].rows.push({
      id: scheduleId,
      dueDate: normalizeBulkDate_(getBulkCell_(row, dueDateColumn)),
      amount: normalizeBulkAmount_(getBulkCell_(row, amountColumn)),
      comments: groupOptions.useDashboardInputs ? "" : getBulkCell_(row, commentsColumn),
      setupFlag: getBulkCell_(row, setupFlagColumn),
      followupRequired: getBulkCell_(row, followupRequiredColumn),
      followupDate: normalizeBulkDate_(getBulkCell_(row, followupDateColumn)),
      masterValues: getBulkRowMasterValues_(row, masterColumnMap),
      sourceIndex: index
    });
  });

  return Object.keys(groups).map(function(key) {
    return buildBulkPayloadForGroup_(groups[key]);
  });
}

function normalizeBulkDashboardOptions_(options) {
  const useDashboardInputs = options && options.useDashboardInputs === true;
  const normalized = {
    useDashboardInputs: useDashboardInputs,
    paymentOutcome: useDashboardInputs ? String(options.paymentOutcome || BULK_OUTCOME_COMPLETED).trim() : "",
    totalPaymentSetup: useDashboardInputs ? String(options.totalPaymentSetup || "").trim() : "",
    repName: useDashboardInputs ? String(options.repName || "").trim() : "",
    confirmationNumber: useDashboardInputs ? String(options.confirmationNumber || "").trim() : "",
    escalationReason: useDashboardInputs ? String(options.escalationReason || "").trim() : "",
    ringCentralMasterId: useDashboardInputs ? String(options.ringCentralMasterId || "").trim() : "",
    usePerClientOptions: Array.isArray(options.clientOptions) && options.clientOptions.length > 0,
    clientOptionMap: {}
  };
  if (normalized.usePerClientOptions) {
    options.clientOptions.forEach(function(clientOption) {
      const key = String(clientOption.key || "").toLowerCase();
      if (!key) return;
      normalized.clientOptionMap[key] = {
        useDashboardInputs: true,
        paymentOutcome: String(clientOption.paymentOutcome || BULK_OUTCOME_COMPLETED).trim(),
        totalPaymentSetup: String(clientOption.totalPaymentSetup || "").trim(),
        repName: String(clientOption.repName || "").trim(),
        confirmationNumber: String(clientOption.confirmationNumber || "").trim(),
        escalationReason: String(clientOption.escalationReason || "").trim(),
        ringCentralMasterId: String(clientOption.ringCentralMasterId || "").trim()
      };
    });
  }
  return normalized;
}

function validateBulkDashboardOptions_(options) {
  if (!options.useDashboardInputs) return;
  if (options.usePerClientOptions) return;
  const outcome = normalizeBulkPaymentOutcome_(options.paymentOutcome);
  if (outcome === BULK_OUTCOME_COMPLETED) {
    const setupCount = toPositiveInteger_(options.totalPaymentSetup);
    if (options.totalPaymentSetup && (setupCount < 1 || setupCount > 24)) throw new Error("Bulk dashboard needs Total Payment Setup count between 1 and 24.");
  }
}

function getBulkGroupOptions_(options, groupKey) {
  if (options.usePerClientOptions) {
    const clientOptions = options.clientOptionMap[String(groupKey || "").toLowerCase()];
    if (clientOptions) return clientOptions;
    throw new Error("Bulk dashboard is missing review details for one client row. Click Review Clients again.");
  }
  return options;
}

function validateBulkGroupDashboardOptions_(group, outcome, scheduleCount) {
  if (!group.useDashboardInputs) return;
  if (outcome === BULK_OUTCOME_COMPLETED) {
    const setupCount = toPositiveInteger_(group.totalPaymentSetup);
    if (group.totalPaymentSetup && (setupCount < 1 || setupCount > scheduleCount)) {
      throw new Error("Total Payment Setup must be between 1 and " + String(scheduleCount) + " for " + describeBulkGroup_(group) + ".");
    }
  }
}

function buildBulkPayloadForGroup_(group) {
  const rows = group.rows.slice().sort(compareBulkScheduleRows_);
  const ids = rows.map(function(row) { return row.id; });
  const dueDates = rows.map(function(row) { return row.dueDate; });
  const amounts = rows.map(function(row) { return row.amount; });
  const masterValues = rows.map(function(row) { return row.masterValues || {}; });
  const termBreakdown = rows.length;
  const outcome = normalizeBulkPaymentOutcome_(group.paymentOutcome);
  const escalationFollowup = isBulkEscalationFollowup_(outcome);
  const escalationNoFollowup = isBulkEscalationNoFollowup_(outcome);
  validateBulkGroupDashboardOptions_(group, outcome, rows.length);
  const setupCount = getBulkSetupCount_(group, rows, escalationFollowup, escalationNoFollowup);
  const generatedComment = buildBulkGeneratedComment_(group, rows, setupCount, escalationFollowup, escalationNoFollowup);
  const groupComment = group.comments || firstNonEmpty_(rows.map(function(row) { return row.comments; })) || generatedComment;
  const rowComments = rows.map(function(row, index) {
    if (row.comments) return row.comments;
    if (outcome === BULK_OUTCOME_COMPLETED || escalationFollowup || escalationNoFollowup) return groupComment || "";
    return index < setupCount ? groupComment || "" : "";
  });

  const followupPlan = buildBulkFollowupPlan_(rows, setupCount, group, escalationFollowup, escalationNoFollowup);
  const record = {
    id: Utilities.getUuid(),
    createdAt: new Date().toISOString(),
    subscriber: group.subscriber,
    clientId: group.clientId,
    clientFullName: group.clientFullName,
    dmPaymentScheduleId: ids.join(", "),
    dmPaymentScheduleCount: String(ids.length),
    paymentDueDateNew: dueDates[0] || "",
    paymentAmount: amounts[0] || "",
    creditorName: group.creditorName,
    credContactWorkNumber: group.credContactWorkNumber,
    currentAccountNumbers: group.currentAccountNumbers,
    credEmailAddress: group.credEmailAddress,
    ringCentralMasterId: group.ringCentralMasterId,
    receivedOnDate: formatUsDate(new Date()),
    comments: groupComment || "",
    termBreakdown: String(termBreakdown),
    totalPaymentSetup: String(setupCount),
    paymentOutcome: outcome,
    isFollowupRequired: followupPlan.recordRequired,
    followupDate: followupPlan.recordDate,
    dmPaymentScheduleIds: ids,
    dmPaymentScheduleDueDates: dueDates,
    dmPaymentScheduleAmounts: amounts,
    dmPaymentScheduleComments: rowComments,
    dmPaymentScheduleFollowupDates: followupPlan.dates,
    dmPaymentScheduleFollowupRequired: followupPlan.required,
    dmPaymentScheduleMasterValues: masterValues,
    replaceExistingComments: true
  };

  return {
    createdAt: record.createdAt,
    fields: BULK_PAYMENT_FIELDS,
    labels: BULK_PAYMENT_LABELS,
    record: record
  };
}

function buildBulkFollowupPlan_(rows, setupCount, group, escalationFollowup, escalationNoFollowup) {
  if (escalationFollowup) {
    const date = "Awaiting Creditor Confirmation";
    return {
      recordRequired: "Yes",
      recordDate: date,
      dates: rows.map(function() { return date; }),
      required: rows.map(function() { return "Yes"; })
    };
  }

  if (escalationNoFollowup) {
    return {
      recordRequired: "No",
      recordDate: "N/A",
      dates: rows.map(function() { return "N/A"; }),
      required: rows.map(function() { return "No"; })
    };
  }

  return {
    recordRequired: "No",
    recordDate: "N/A",
    dates: rows.map(function() { return "N/A"; }),
    required: rows.map(function() { return "No"; })
  };
}

function fillBulkGroupValue_(group, field, value) {
  if (group[field]) return;
  const cleanValue = String(value || "").trim();
  if (cleanValue) group[field] = cleanValue;
}

function compareBulkScheduleRows_(first, second) {
  const firstDate = parseUsDate(first.dueDate);
  const secondDate = parseUsDate(second.dueDate);
  if (firstDate && secondDate && firstDate.getTime() !== secondDate.getTime()) return firstDate - secondDate;
  if (firstDate && !secondDate) return -1;
  if (!firstDate && secondDate) return 1;
  return Number(first.sourceIndex || 0) - Number(second.sourceIndex || 0);
}

function normalizeBulkPaymentOutcome_(value) {
  const text = String(value || "").toLowerCase().replace(/[^a-z0-9]+/g, " ").trim();
  if (!text) return BULK_OUTCOME_COMPLETED;
  if (text.indexOf("awaiting") !== -1 || text.indexOf("creditor response") !== -1 || text.indexOf("follow up needed") !== -1 || text.indexOf("followup needed") !== -1 || text.indexOf("follow required") !== -1 || text.indexOf("no follow") !== -1 || text.indexOf("no action") !== -1) {
    return BULK_OUTCOME_AWAITING;
  }
  return BULK_OUTCOME_COMPLETED;
}

function isBulkEscalationFollowup_(outcome) {
  const text = String(outcome || "").toLowerCase();
  return outcome === BULK_OUTCOME_AWAITING || text.indexOf("follow up needed") !== -1;
}

function isBulkEscalationNoFollowup_(outcome) {
  return false;
}

function getBulkSetupCount_(group, rows, escalationFollowup, escalationNoFollowup) {
  if (escalationFollowup || escalationNoFollowup) return 0;

  const explicitCount = toPositiveInteger_(group.totalPaymentSetup);
  if (explicitCount > rows.length) {
    throw new Error("Total Payment Setup cannot be greater than CRM Payment Schedule ID count for " + describeBulkGroup_(group) + ".");
  }
  if (explicitCount > 0) return explicitCount;

  if (rows.length >= 1) return rows.length;

  const setupFlagCount = rows.filter(function(row) {
    return isTruthyBulkValue_(row.setupFlag);
  }).length;
  if (setupFlagCount > 0) return Math.min(setupFlagCount, rows.length);

  const commentedCount = rows.filter(function(row) {
    return String(row.comments || "").trim();
  }).length;
  if (commentedCount > 0) return Math.min(commentedCount, rows.length);

  throw new Error("Bulk upload needs Total Payment Setup for " + describeBulkGroup_(group) + ". Example: enter 2 when only the first 2 payments were set up.");
}

function isTruthyBulkValue_(value) {
  const text = String(value || "").toLowerCase().trim();
  return ["yes", "y", "true", "setup", "set up", "completed", "1"].indexOf(text) !== -1;
}

function buildBulkGeneratedComment_(group, rows, setupCount, escalationFollowup, escalationNoFollowup) {
  const today = formatBulkCommentDate_(new Date());
  const creditorName = group.creditorName || "";
  const creditorPhone = group.credContactWorkNumber || "";
  const repName = group.repName || "";

  if (escalationFollowup) {
    const reason = group.escalationReason ? " Reason - " + group.escalationReason : "";
    return today + " Bulk Spreadsheet sent to the Creditor awaiting confirmation" + reason;
  }

  if (escalationNoFollowup) {
    return today + " Called " + creditorName + " at " + creditorPhone + " & spoke with Rep " + repName + " to setup payment but they said they cannot setup the payment as there is no settlement. They cannot reinstate the settlement.";
  }

  return today + " Payment set up successfully through spreadsheet";
}

function formatBulkCommentDate_(date) {
  const monthNames = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
  return formatUsDate(date) + " " + monthNames[date.getMonth()];
}

function describeBulkGroup_(group) {
  return String(group.clientFullName || "client").trim() + " / Client ID " + String(group.clientId || "").trim();
}

function getBulkColumn_(headers, names) {
  for (let nameIndex = 0; nameIndex < names.length; nameIndex += 1) {
    const target = normalizeBulkHeader_(names[nameIndex]);
    for (let index = 0; index < headers.length; index += 1) {
      if (normalizeBulkHeader_(headers[index]) === target) return index + 1;
    }
  }
  return 0;
}

function normalizeBulkHeader_(value) {
  return String(value || "").toLowerCase().replace(/[^a-z0-9]+/g, " ").trim();
}

function getLegacyImportColumn_(headers, names) {
  return getBulkColumn_(headers, names);
}

function getLegacyImportFieldValue_(row, headers, field) {
  const fallbackHeader = getMasterFieldHeader_(field, BULK_PAYMENT_LABELS);
  const aliases = getLegacyImportFieldAliases_()[field] || (fallbackHeader ? [fallbackHeader] : []);
  const column = getLegacyImportColumn_(headers, aliases);
  if (!column) return "";
  return normalizeLegacyImportFieldValue_(field, row[column - 1]);
}

function getLegacyCreatedAt_(row, headers) {
  const column = getLegacyImportColumn_(headers, ["Created At", "Created", "Submitted At", "Timestamp", "Date Created"]);
  return column ? formatLegacyImportCell_(row[column - 1]) : new Date();
}

function normalizeLegacyImportFieldValue_(field, value) {
  if (field === "paymentDueDateNew" || field === "receivedOnDate" || field === "followupDate") {
    return normalizeBulkDate_(formatLegacyImportCell_(value));
  }
  if (field === "paymentAmount") return normalizeBulkAmount_(formatLegacyImportCell_(value));
  if (field === "currentAccountNumbers" || field === "originalAccountNumber") return cleanAccountNumber_(formatLegacyImportCell_(value));
  return formatLegacyImportCell_(value);
}

function formatLegacyImportCell_(value) {
  if (Object.prototype.toString.call(value) === "[object Date]" && !isNaN(value)) return formatUsDate(value);
  return value == null ? "" : String(value).trim();
}

function setImportValue_(row, headers, header, value) {
  const column = headers.indexOf(header);
  if (column >= 0) row[column] = formatImportValueForHeader_(header, value);
}

function formatImportValueForHeader_(header, value) {
  if (MASTER_DATE_HEADERS.indexOf(header) !== -1) return formatDateForMasterSheet_(value);
  return value;
}

function getMasterFieldHeader_(field, labels) {
  if (Object.prototype.hasOwnProperty.call(MASTER_FIELD_LABELS, field)) {
    return MASTER_FIELD_LABELS[field] || "";
  }
  return labels && labels[field] ? labels[field] : "";
}

function getLegacyImportFieldAliases_() {
  return {
    subscriber: ["COMPANY", "Subscriber"],
    clientId: ["ENROLLMENT_EXTERNAL_ID", "Client ID", "Client Id"],
    clientFullName: ["CLIENT_FULL_NAME", "Client Full Name", "Client Name", "Client FullName"],
    dmPaymentScheduleId: [
      "CRM_PAYMENT_SCHEDULE_ID",
      "CRM Payment Schedule ID",
      "DM Payment Schedule ID",
      "DM Payment Schedule Id",
      "CRM Schedule ID",
      "CRM Scheduled ID",
      "DM Schedule ID",
      "DM Scheduled ID",
      "Payment Schedule ID",
      "Schedule ID",
      "Scheduled ID"
    ],
    dmPaymentScheduleCount: ["CRM Payment Schedule ID Count", "DM Payment Schedule ID Count", "Schedule ID Count"],
    paymentDueDateNew: ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New", "Due Date", "Payment Due"],
    paymentAmount: ["PAYMENT_AMOUNT", "Payment Amount", "Amount"],
    creditorName: ["CREDITOR_NAME", "Creditor Name", "Creditor", "Creditor Company"],
    credContactWorkNumber: ["Cred Contact Number", "Cred Contact Work Number", "Creditor Phone Number", "Creditor Number", "Phone Number"],
    currentAccountNumbers: ["DEBT_ACCOUNT_NUMBER", "Current Account Numbers", "Current Account Number", "Account Number", "Account Numbers"],
    originalAccountNumber: ["ORIGINAL_ACCOUNT_NUMBER", "Original Account Number", "Original Account Numbers"],
    credEmailAddress: ["Cred Email Address", "Creditor Email", "Email Address"],
    agentName: ["USER", "Agent Name", "Agent", "User", "Memo (DM) / User (SF)"],
    ringCentralMasterId: ["Ring Central Master ID", "RingCentral Master ID", "Ring Central ID"],
    receivedOnDate: ["Received on", "CFT Team Payment Worked date", "Payment Received on (Date)", "Received on Date", "Received on (Date)", "Worked Date"],
    comments: ["Comments", "Comment", "Notes"],
    termBreakdown: ["Term Breakdown", "Term", "Settlement Term"],
    totalPaymentSetup: ["Total Payment Setup", "Payment Setup Count", "Setup Count", "Payments Setup"],
    paymentOutcome: ["PAYMENT_STATUS", "Payment Outcome", "Outcome", "Status", "Payment Status"],
    isFollowupRequired: ["Is Follow-up Required", "Is Followup Required", "Follow-up Required", "Follow Up Required"],
    followupDate: ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"]
  };
}

function getBulkCell_(row, column) {
  if (!column) return "";
  return String(row[column - 1] == null ? "" : row[column - 1]).trim();
}

function getBulkMasterColumnMap_(headers) {
  const map = {};
  MASTER_HEADERS.forEach(function(header) {
    map[header] = getBulkColumn_(headers, [header]);
  });
  return map;
}

function getBulkRowMasterValues_(row, masterColumnMap) {
  const values = {};
  MASTER_HEADERS.forEach(function(header) {
    const column = masterColumnMap[header];
    if (!column) return;
    let value = getBulkCell_(row, column);
    if (!value) return;
    if (header === "PAYMENT_SCHEDULE_DATE" || header === "Received on" || header === "Follow up Date") value = normalizeBulkDate_(value);
    if (header === "PAYMENT_AMOUNT") value = normalizeBulkAmount_(value);
    if (header === "DEBT_ACCOUNT_NUMBER" || header === "ORIGINAL_ACCOUNT_NUMBER") value = cleanAccountNumber_(value);
    values[header] = value;
  });
  return values;
}

function normalizeBulkDate_(value) {
  if (!value || String(value).trim().toUpperCase() === "N/A") return value ? "N/A" : "";
  const text = String(value).trim();
  const parsed = parseUsDate(text);
  if (parsed) return formatUsDate(parsed);
  return text;
}

function normalizeBulkYear_(value) {
  const year = Number(value);
  if (String(value).length === 2) return String(year >= 70 ? 1900 + year : 2000 + year);
  return String(value);
}

function normalizeBulkAmount_(value) {
  const cleaned = String(value || "").replace(/[$,\s]/g, "");
  if (!cleaned) return "";
  const number = Number(cleaned);
  return Number.isFinite(number) ? String(Math.round(number * 100) / 100) : cleaned;
}

function cleanAccountNumber_(value) {
  return String(value || "").trim().replace(/^[`']+/, "");
}

function toPositiveInteger_(value) {
  const number = Number(String(value || "").replace(/[^0-9]/g, ""));
  return Number.isInteger(number) && number > 0 ? number : 0;
}

function firstNonEmpty_(values) {
  for (let index = 0; index < values.length; index += 1) {
    const value = String(values[index] || "").trim();
    if (value) return value;
  }
  return "";
}

function earliestFutureFollowupDate_(rows) {
  const dates = rows
    .map(function(row) { return parseUsDate(row.dueDate); })
    .filter(Boolean)
    .sort(function(first, second) { return first - second; });
  if (!dates.length) return "";
  dates[0].setDate(dates[0].getDate() - 7);
  return formatUsDate(previousWorkingDate_(dates[0]));
}

function nextWorkingDate_(date) {
  const next = new Date(date.getFullYear(), date.getMonth(), date.getDate() + 1);
  while (next.getDay() === 0 || next.getDay() === 6) {
    next.setDate(next.getDate() + 1);
  }
  return formatUsDate(next);
}

function getExistingScheduleIds(sheet) {
  const values = sheet.getDataRange().getValues();
  if (values.length < 2) return new Set();
  const headers = values[0].map(String);
  const scheduleColumn = getScheduleIdColumn(headers);
  const ids = new Set();
  if (!scheduleColumn) return ids;
  values.slice(1).forEach(function(row) {
    const scheduleId = String(row[scheduleColumn - 1] || "").trim();
    if (scheduleId) ids.add(scheduleId.toLowerCase());
  });
  return ids;
}

function extractSpreadsheetId(url) {
  const text = String(url || "").trim();
  const match = text.match(/\/spreadsheets\/d\/([a-zA-Z0-9-_]+)/) || text.match(/^([a-zA-Z0-9-_]{25,})$/);
  return match ? match[1] : "";
}

function getScheduleIdColumn(headers) {
  const exact = getHeaderColumn(headers, [
    "CRM_PAYMENT_SCHEDULE_ID",
    "CRM Payment Schedule ID",
    "DM Payment Schedule ID",
    "CRM Schedule ID",
    "CRM Scheduled ID",
    "Payment Schedule ID",
    "Payment Scheduled ID",
    "Schedule ID",
    "Scheduled ID"
  ]);
  if (exact) return exact;

  for (let index = 0; index < headers.length; index += 1) {
    const normalized = String(headers[index] || "").toLowerCase().replace(/[^a-z0-9]+/g, " ").trim();
    if (normalized.includes("schedule") && normalized.includes("id")) return index + 1;
  }
  return 0;
}

function formatSheetCell(value) {
  if (Object.prototype.toString.call(value) === "[object Date]" && !isNaN(value)) return formatUsDate(value);
  return value == null ? "" : String(value);
}

function formatSheetCellForHeader(header, value) {
  if (MASTER_DATE_HEADERS.indexOf(header) !== -1) return formatDateForMasterSheet_(value);
  return formatSheetCell(value);
}

function normalizeUsDate(value) {
  if (!value || value === "N/A") return "";
  if (Object.prototype.toString.call(value) === "[object Date]" && !isNaN(value)) return formatUsDate(value);
  const parsed = parseUsDate(value);
  return parsed ? formatUsDate(parsed) : String(value).trim();
}

function usDateToMonthKey(value) {
  const date = parseUsDate(value);
  if (!date) return "";
  return String(date.getFullYear()) + "-" + String(date.getMonth() + 1).padStart(2, "0");
}

function getPayloadContents(e) {
  if (e && e.parameter && e.parameter.payload) return e.parameter.payload;
  if (e && e.postData && e.postData.contents) return e.postData.contents;
  return "";
}

function jsonOutput(data) {
  return ContentService.createTextOutput(JSON.stringify(data)).setMimeType(ContentService.MimeType.JSON);
}

function ensureHeaders(sheet, headers) {
  if (sheet.getLastRow() === 0) {
    sheet.appendRow(headers);
    return headers;
  }

  const existing = sheet.getRange(1, 1, 1, sheet.getLastColumn()).getValues()[0].map(function(header) {
    return String(header || "").trim();
  });
  existing.forEach(function(header, index) {
    const replacement = MASTER_HEADER_RENAMES[header];
    if (!replacement) return;
    if (existing.indexOf(replacement) !== -1) return;
    sheet.getRange(1, index + 1).setValue(replacement);
    existing[index] = replacement;
  });
  headers.forEach(function(header, desiredIndex) {
    if (existing.indexOf(header) === -1) {
      let insertAt = existing.length + 1;
      for (let nextIndex = desiredIndex + 1; nextIndex < headers.length; nextIndex += 1) {
        const existingIndex = existing.indexOf(headers[nextIndex]);
        if (existingIndex !== -1) {
          insertAt = existingIndex + 1;
          break;
        }
      }

      if (insertAt <= sheet.getLastColumn()) {
        sheet.insertColumnBefore(insertAt);
        sheet.getRange(1, insertAt).setValue(header);
        existing.splice(insertAt - 1, 0, header);
      } else {
        sheet.getRange(1, sheet.getLastColumn() + 1).setValue(header);
        existing.push(header);
      }
    }
  });
  return existing;
}

function getDmScheduleIds(record) {
  if (Array.isArray(record.dmPaymentScheduleIds) && record.dmPaymentScheduleIds.length) {
    return record.dmPaymentScheduleIds.map(String).map(trimValue).filter(Boolean);
  }
  return String(record.dmPaymentScheduleId || "").split(",").map(trimValue).filter(Boolean);
}

function ensureUniqueScheduleIds_(dmIds) {
  const seen = {};
  dmIds.forEach(function(dmId) {
    const key = String(dmId || "").trim().toLowerCase();
    if (!key) return;
    if (seen[key]) throw new Error("Duplicate CRM Payment Schedule ID received: " + dmId);
    seen[key] = true;
  });
}

function ensurePaymentSetupWithinTerm_(record, dmCount) {
  const totalPaymentSetup = toPositiveInteger_(record.totalPaymentSetup);
  if (!totalPaymentSetup) return;
  const termBreakdown = toPositiveInteger_(record.termBreakdown) || dmCount;
  if (totalPaymentSetup > termBreakdown) {
    throw new Error("Total Payment Setup cannot be more than Term Breakdown.");
  }
}

function getDmScheduleRowMap(sheet, dmColumn) {
  const rowMap = {};
  const lastRow = sheet.getLastRow();
  if (lastRow < 2 || dmColumn < 1) return rowMap;

  const values = sheet.getRange(2, dmColumn, lastRow - 1, 1).getValues();
  values.forEach(function(row, index) {
    const key = String(row[0] || "").trim().toLowerCase();
    if (key && !rowMap[key]) rowMap[key] = index + 2;
  });
  return rowMap;
}

function getDmScheduleRowMapForIds(sheet, dmColumn, dmIds) {
  const rowMap = {};
  const lastRow = sheet.getLastRow();
  if (lastRow < 2 || dmColumn < 1 || !(dmIds || []).length) return rowMap;

  const range = sheet.getRange(2, dmColumn, lastRow - 1, 1);
  (dmIds || []).forEach(function(dmId) {
    const key = String(dmId || "").trim().toLowerCase();
    if (!key || rowMap[key]) return;
    const cell = range
      .createTextFinder(String(dmId || "").trim())
      .matchEntireCell(true)
      .matchCase(false)
      .findNext();
    if (cell) rowMap[key] = cell.getRow();
  });
  return rowMap;
}

function getDmScheduleDueDates(record) {
  if (Array.isArray(record.dmPaymentScheduleDueDates)) {
    return record.dmPaymentScheduleDueDates.map(String).map(trimValue);
  }
  return [];
}

function getDmScheduleAmounts(record) {
  if (Array.isArray(record.dmPaymentScheduleAmounts)) {
    return record.dmPaymentScheduleAmounts.map(String).map(trimValue);
  }
  return [];
}

function getDmScheduleFollowupDates(record) {
  if (Array.isArray(record.dmPaymentScheduleFollowupDates)) {
    return record.dmPaymentScheduleFollowupDates.map(String).map(trimValue);
  }
  return [];
}

function getDmScheduleFollowupRequired(record) {
  if (Array.isArray(record.dmPaymentScheduleFollowupRequired)) {
    return record.dmPaymentScheduleFollowupRequired.map(String).map(trimValue);
  }
  return [];
}

function getDmScheduleComments(record) {
  if (Array.isArray(record.dmPaymentScheduleComments)) {
    return record.dmPaymentScheduleComments.map(String);
  }
  return [];
}

function getDmScheduleMasterValues(record) {
  if (Array.isArray(record.dmPaymentScheduleMasterValues)) {
    return record.dmPaymentScheduleMasterValues.map(function(value) {
      return value && typeof value === "object" ? value : {};
    });
  }
  return [];
}

function trimValue(value) {
  return String(value).trim();
}

function upsertDmScheduleRow(sheet, headers, fields, labels, record, dmId, dmCount, dmIndex, dmDueDate, dmAmount, dmFollowupDate, dmFollowupRequired, dmComment, dmMasterValues, dmRowMap, dmColumn) {
  const rowRecord = Object.assign({}, record, {
    dmPaymentScheduleId: dmId,
    dmPaymentScheduleCount: String(dmCount),
    paymentDueDateNew: dmDueDate || record.paymentDueDateNew,
    paymentAmount: dmAmount !== undefined ? dmAmount : record.paymentAmount,
    comments: dmComment !== undefined ? dmComment : record.comments
  });
  if (dmFollowupDate || dmFollowupRequired) {
    rowRecord.followupDate = dmFollowupDate || "N/A";
    rowRecord.isFollowupRequired = dmFollowupRequired || (dmFollowupDate && dmFollowupDate !== "N/A" ? "Yes" : "No");
  } else {
    applyAutomaticFollowup(rowRecord, dmCount, dmIndex);
  }

  const activeDmColumn = dmColumn || getScheduleIdColumn(headers);
  const dmKey = String(dmId || "").trim().toLowerCase();
  const existingRowNumber = dmRowMap ? dmRowMap[dmKey] : findRowByDmScheduleId(sheet, activeDmColumn, dmId);
  const existingRowValues = existingRowNumber
    ? sheet.getRange(existingRowNumber, 1, 1, headers.length).getValues()[0]
    : new Array(headers.length).fill("");
  const duplicatePaymentSetupMessage = getDuplicatePaymentSetupMessage_(sheet, headers, existingRowNumber, rowRecord, dmIndex, existingRowValues);
  if (duplicatePaymentSetupMessage) {
    if (dmCount > 1) return { skippedDuplicatePaymentSetup: true };
    throw new Error(duplicatePaymentSetupMessage);
  }
  const rowNumber = existingRowNumber || sheet.getLastRow() + 1;
  if (dmRowMap && dmKey) dmRowMap[dmKey] = rowNumber;
  const rowValues = existingRowNumber ? existingRowValues.slice() : new Array(headers.length).fill("");
  Object.keys(dmMasterValues || {}).forEach(function(header) {
    if (MASTER_HEADERS.indexOf(header) === -1) return;
    setRowValueByHeader_(rowValues, headers, header, dmMasterValues[header] || "");
  });
  fields.forEach(function(field) {
    if (field === "followupDate" || field === "isFollowupRequired") return;
    const header = getMasterFieldHeader_(field, labels);
    if (!header) return;
    let value = "";
    if (field === "paymentOutcome") {
      value = getRowPaymentStatus_(rowRecord, dmIndex);
    } else if (field === "comments" && existingRowNumber && !rowRecord.replaceExistingComments) {
      value = mergeCommentsValue_(rowValues[headers.indexOf(header)], rowRecord[field] || "");
    } else {
      value = rowRecord[field] || "";
    }
    setRowValueByHeader_(rowValues, headers, header, value);
  });
  setFollowupDateAliases_(rowValues, headers, rowRecord.followupDate || "");
  applyTextFormatsForRow_(sheet, headers, rowNumber);
  sheet.getRange(rowNumber, 1, 1, headers.length).setValues([rowValues]);
  return { skippedDuplicatePaymentSetup: false };
}

function setRowValueByHeader_(rowValues, headers, header, value) {
  const index = headers.indexOf(header);
  if (index < 0) return;
  rowValues[index] = formatMasterValueForHeader_(header, value);
}

function formatMasterValueForHeader_(header, value) {
  if (isFollowupHeader_(header)) return formatFollowupDateForMasterSheet_(value);
  if (MASTER_DATE_HEADERS.indexOf(header) !== -1) return formatDateForMasterSheet_(value);
  if (header === "DEBT_ACCOUNT_NUMBER" || header === "ORIGINAL_ACCOUNT_NUMBER") {
    return formatAccountNumberForSheet_(value);
  }
  return value;
}

function setFollowupDateAliases_(rowValues, headers, value) {
  ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"].forEach(function(header) {
    setRowValueByHeader_(rowValues, headers, header, value);
  });
}

function applyTextFormatsForRow_(sheet, headers, rowNumber) {
  const ranges = [];
  headers.forEach(function(header, index) {
    if (!isFollowupHeader_(header)
      && MASTER_DATE_HEADERS.indexOf(header) === -1
      && header !== "DEBT_ACCOUNT_NUMBER"
      && header !== "ORIGINAL_ACCOUNT_NUMBER") {
      return;
    }
    ranges.push(sheet.getRange(rowNumber, index + 1).getA1Notation());
  });
  if (ranges.length) sheet.getRangeList(ranges).setNumberFormat("@");
}

function writeByHeader(sheet, headers, rowNumber, header, value) {
  const column = headers.indexOf(header) + 1;
  if (column < 1) return;
  const range = sheet.getRange(rowNumber, column);
  if (isFollowupHeader_(header)) {
    range.setNumberFormat("@");
    range.setValue(formatFollowupDateForMasterSheet_(value));
    return;
  }
  if (MASTER_DATE_HEADERS.indexOf(header) !== -1) {
    range.setNumberFormat("@");
    range.setValue(formatDateForMasterSheet_(value));
    return;
  }
  if (header === "DEBT_ACCOUNT_NUMBER" || header === "ORIGINAL_ACCOUNT_NUMBER") {
    range.setNumberFormat("@");
    range.setValue(formatAccountNumberForSheet_(value));
    return;
  }
  range.setValue(value);
}

function getRowPaymentStatus_(record, dmIndex) {
  const outcome = String(record.paymentOutcome || "").trim();
  const normalizedOutcome = outcome.toLowerCase();
  const setupCount = Number(record.totalPaymentSetup || 0);
  const setupCompleted = normalizedOutcome === "payment setup completed"
    || normalizedOutcome === "bulk payments setup successfully";
  if (!setupCompleted) return "";
  if (!Number.isInteger(setupCount) || setupCount < 1) return "";
  return dmIndex < setupCount ? "Payment Setup Completed" : "";
}

function getDuplicatePaymentSetupMessage_(sheet, headers, existingRowNumber, rowRecord, dmIndex, existingRowValues) {
  if (!existingRowNumber) return "";
  const newStatus = getRowPaymentStatus_(rowRecord, dmIndex);
  if (newStatus !== "Payment Setup Completed") return "";

  const statusColumn = getHeaderColumn(headers, ["PAYMENT_STATUS", "Payment Status", "Payment Outcome"]);
  const dueDateColumn = getHeaderColumn(headers, ["PAYMENT_SCHEDULE_DATE", "Payment Due Date", "Payment Due Date New"]);
  if (!statusColumn || !dueDateColumn) return "";

  const existingStatus = String(existingRowValues
    ? existingRowValues[statusColumn - 1] || ""
    : sheet.getRange(existingRowNumber, statusColumn).getValue() || "").trim().toLowerCase();
  if (existingStatus !== "payment setup completed") return "";

  const existingDueDate = normalizeUsDate(existingRowValues
    ? existingRowValues[dueDateColumn - 1]
    : sheet.getRange(existingRowNumber, dueDateColumn).getValue());
  const newDueDate = normalizeUsDate(rowRecord.paymentDueDateNew || "");
  if (!existingDueDate || !newDueDate || existingDueDate !== newDueDate) return "";

  return (
    "For this due date payment was already setup. CRM Payment Schedule ID " +
    String(rowRecord.dmPaymentScheduleId || "") +
    " already has Payment Setup Completed for " +
    existingDueDate +
    "."
  );
}

function formatAccountNumberForSheet_(value) {
  const cleanValue = String(value || "").trim();
  if (!cleanValue) return "";
  const withoutPrefix = cleanValue.replace(/^[`']+/, "");
  return "'" + withoutPrefix;
}

function formatDateForMasterSheet_(value) {
  const text = String(value || "").trim();
  if (!text || text.toUpperCase() === "N/A" || text === "Awaiting Creditor Confirmation") return text;
  const normalizedDate = normalizeUsDate(value);
  const parsed = parseUsDate(normalizedDate);
  if (!parsed) return text;
  return String(parsed.getMonth() + 1).padStart(2, "0") + "-" +
    String(parsed.getDate()).padStart(2, "0") + "-" + parsed.getFullYear();
}

function isFollowupHeader_(header) {
  return ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"].indexOf(header) !== -1;
}

function formatFollowupDateForMasterSheet_(value) {
  const text = String(value || "").trim();
  if (!text || text.toUpperCase() === "N/A" || text === "Awaiting Creditor Confirmation") return text;
  const normalizedDate = normalizeUsDate(value);
  const parsed = parseUsDate(normalizedDate);
  if (!parsed) return text;
  return formatDateForMasterSheet_(formatUsDate(previousWorkingDate_(parsed)));
}

function mergeCommentsForExistingRow_(sheet, headers, rowNumber, header, newComment) {
  const column = headers.indexOf(header) + 1;
  const cleanNewComment = String(newComment || "").trim();
  if (column < 1) return cleanNewComment;

  const existingComment = String(sheet.getRange(rowNumber, column).getValue() || "").trim();
  return mergeCommentsValue_(existingComment, cleanNewComment);
}

function mergeCommentsValue_(existingComment, newComment) {
  const cleanNewComment = String(newComment || "").trim();
  existingComment = String(existingComment || "").trim();
  if (!existingComment) return cleanNewComment;
  if (!cleanNewComment) return existingComment;

  const existingNormalized = normalizeCommentForCompare_(existingComment);
  const newNormalized = normalizeCommentForCompare_(cleanNewComment);
  if (existingNormalized === newNormalized || existingNormalized.indexOf(newNormalized) !== -1) {
    return existingComment;
  }

  return existingComment + "\n\n" + cleanNewComment;
}

function normalizeCommentForCompare_(value) {
  return String(value || "").replace(/\s+/g, " ").trim().toLowerCase();
}

function getHeaderColumn(headers, names) {
  for (let index = 0; index < names.length; index += 1) {
    const column = headers.indexOf(names[index]) + 1;
    if (column > 0) return column;
  }
  return 0;
}

function writeFollowupDateAliases(sheet, headers, rowNumber, value) {
  ["Follow up Date", "Follow-up Date", "Follow Up Date", "Followup Date"].forEach(function(header) {
    writeByHeader(sheet, headers, rowNumber, header, value);
  });
}

function applyAutomaticFollowup(record, dmCount, dmIndex) {
  const paymentCount = Number(record.totalPaymentSetup);
  if (!Number.isInteger(paymentCount) || paymentCount < 1 || dmCount < 1) return;
  if (dmIndex < paymentCount) {
    record.isFollowupRequired = "No";
    record.followupDate = "N/A";
    return;
  }

  const followDate = parseUsDate(record.paymentDueDateNew);
  if (!followDate) return;
  followDate.setDate(followDate.getDate() - paymentFollowupLeadDays_(record));
  record.isFollowupRequired = "Yes";
  record.followupDate = formatUsDate(previousWorkingDate_(followDate));
}

function paymentFollowupLeadDays_(record) {
  return String(record.paymentSetupMode || "").trim().toLowerCase() === "web" ? 1 : 7;
}

function previousWorkingDate_(date) {
  const adjusted = new Date(date);
  while (adjusted.getDay() === 0 || adjusted.getDay() === 6) {
    adjusted.setDate(adjusted.getDate() - 1);
  }
  return adjusted;
}

function parseUsDate(value) {
  if (Object.prototype.toString.call(value) === "[object Date]" && !isNaN(value)) {
    return new Date(value.getFullYear(), value.getMonth(), value.getDate());
  }
  const text = String(value || "").trim();
  if (!text || text.toUpperCase() === "N/A") return null;

  if (/^\d+(?:\.\d+)?$/.test(text) && Number(text) > 20000) {
    const excelDate = new Date(Math.round((Number(text) - 25569) * 86400 * 1000));
    return isNaN(excelDate) ? null : new Date(excelDate.getFullYear(), excelDate.getMonth(), excelDate.getDate());
  }

  const yearFirst = text.match(/^(\d{4})[-/](\d{1,2})[-/](\d{1,2})$/);
  if (yearFirst) return validDateFromParts_(Number(yearFirst[1]), Number(yearFirst[2]), Number(yearFirst[3]));

  const slashOrDash = text.match(/^(\d{1,2})[-/](\d{1,2})[-/](\d{2,4})$/);
  if (!slashOrDash) return null;

  const first = Number(slashOrDash[1]);
  const second = Number(slashOrDash[2]);
  const rawYear = slashOrDash[3];
  const yearNumber = Number(rawYear);
  const year = rawYear.length === 2 ? (yearNumber >= 70 ? 1900 + yearNumber : 2000 + yearNumber) : yearNumber;
  const month = first > 12 && second <= 12 ? second : first;
  const day = first > 12 && second <= 12 ? first : second;
  return validDateFromParts_(year, month, day);
}

function validDateFromParts_(year, month, day) {
  if (!Number.isInteger(year) || !Number.isInteger(month) || !Number.isInteger(day)) return null;
  const date = new Date(year, month - 1, day);
  return date.getFullYear() === year && date.getMonth() === month - 1 && date.getDate() === day ? date : null;
}

function addMonthsClamped(date, months) {
  const totalMonth = date.getMonth() + months;
  const year = date.getFullYear() + Math.floor(totalMonth / 12);
  const month = ((totalMonth % 12) + 12) % 12;
  const lastDay = new Date(year, month + 1, 0).getDate();
  return new Date(year, month, Math.min(date.getDate(), lastDay));
}

function formatUsDate(date) {
  return String(date.getMonth() + 1).padStart(2, "0") + "/" +
    String(date.getDate()).padStart(2, "0") + "/" + date.getFullYear();
}

function findRowByDmScheduleId(sheet, dmColumn, dmId) {
  const lastRow = sheet.getLastRow();
  if (lastRow < 2 || dmColumn < 1) return null;
  const values = sheet.getRange(2, dmColumn, lastRow - 1, 1).getValues();
  for (let index = 0; index < values.length; index += 1) {
    if (String(values[index][0]).trim() === dmId) return index + 2;
  }
  return null;
}