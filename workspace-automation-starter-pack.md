# Google Workspace Automation Starter Pack

This starter pack provides ready-to-use templates, scripts, and checklists to
help freelancers, consultants, and small teams automate common Google Workspace
tasks. All items are mobile-friendly and require no paid tools.

---

## 1. Migration Checklist

- [ ] Audit current email, files, and calendars
- [ ] Create Google Workspace accounts for users
- [ ] Set up shared Drives and permissions
- [ ] Migrate email using Google Workspace Migration tool
- [ ] Import calendars and contacts
- [ ] Test logins and sharing
- [ ] Decommission old systems

---

## 2. Automated Google Sheets Invoice Log

- Create a Sheet with columns: Date, Client, Amount, Status
- Use Google Forms for fast mobile entry
- Add conditional formatting for overdue invoices

---

## 3. Gmail Auto-Organize Filters

- Click Settings > See all settings > Filters
- Create filters for clients, invoices, or projects
- Automatically label and archive low-priority emails

---

## 4. Apps Script: Bulk Email Sender

Paste this into `Extensions > Apps Script` in Gmail:

```javascript
function sendBulkEmails() {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Emails");
  var data = sheet.getDataRange().getValues();
  for (var i = 1; i < data.length; i++) {
    MailApp.sendEmail(data[i][0], data[i][1], data[i][2]);
  }
}