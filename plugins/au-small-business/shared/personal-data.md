<!-- Modified from Anthropic's Small Business plugin (Apache-2.0) for Australian use. See NOTICE. -->

# Personal data — what never leaves the source system

**Shared across the plugin.** Connected payroll, HR, tax, ledger, payments,
and support systems return more about a person than any deliverable needs.
The rule is the same in every skill: use a field to do the work, never
reproduce it.

---

## Never reproduced, in any output

Not in chat, not in an HTML artifact, not in a Notion or Canva page, not in a
spreadsheet, not in a CRM note, not in a draft email, not in a log line:

- Tax file numbers (TFNs), Medicare numbers, super fund member numbers, individual tax IDs, and national ID numbers. A
  business ABN on an invoice or a TPAR is the one designed exception.
- Dates of birth.
- Home addresses of employees and contractors. A work location is fine.
- Full card numbers, CVVs, and expiry dates. The last four digits identify a
  card; nothing more is ever needed.
- Full bank account numbers and BSBs, for the business or for anyone it
  pays. The last four digits or the bank name is the limit.
- Government ID images or numbers: driver licences, passports, ImmiCards and visa grant numbers, and the detail of a right-to-work or visa (VEVO) check. An output may say that a person's work rights were checked, and when, or that a visa condition limits their hours; it points to VEVO or the payroll system for the detail.

When a tool result carries one of these (Xero Payroll, MYOB, Employment Hero, Gusto and QuickBooks Payroll
employee records carry DOB, TFN or SSN fields, bank details and home addresses; a vendor or card record carries the full
number), it is read for the step that needs it and dropped. It is not copied
into working notes, not echoed back to confirm, and not left in a rendered
page.

---

## Kept to the output that needs it

- **Per-person pay** (rate, hours, gross, net, deductions) appears only in
  payroll and tax outputs, none of which are in this release — never
  in a brief, a pulse, a hiring output, or a customer-facing draft.
- **Medical, disability, leave-reason, and protected-class details** seen in
  a resume, a time-off request, or a ticket are not carried into any score,
  note, or output.
- **Customer contact details** go only where the skill's step sends them:
  the CRM of record, or the draft addressed to that customer. Never into a
  shared channel post or an artifact meant for a wider audience.

---

## When the owner asks for it anyway

Say the field is not reproduced by this plugin and point them to the source
system, where it sits under its own access controls. One line, no lecture.

---

## Skills this governs first

`inbox-manager`, `crm-autopilot`, `business-pulse` and `report-builder`. Every
other skill applies it the moment a connector returns one of the fields
above.
