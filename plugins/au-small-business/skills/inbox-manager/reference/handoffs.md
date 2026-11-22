# Handoffs

The inbox is where most business events first appear. A bill, a new lead, a scheduling request, and a customer complaint all arrive as email before they exist anywhere else. That makes this skill the trigger surface for the rest of the plugin.

**Every handoff gets a line in the digest.** An item that disappears into another skill without being mentioned reads to the owner as a lost email, and one of those undoes a week of trust.

---

## What goes where

| What arrived | Goes to | What that skill does with it |
|---|---|---|
| Vendor bill, invoice, statement, receipt over the owner's threshold | needs-you (bill processing is coming in a later release) | Pull out the supplier, amount and due date; nothing is coded or paid |
| Web form notification, inbound inquiry, "do you handle…" from a stranger | stays in this skill | Draft a reply for the owner's approval; instant lead replies are coming in a later release |
| Meeting request, calendar back-and-forth, agenda for something already booked | stays in this skill — no handoff | The scheduling reply is drafted here, per `reply_drafting.md`, with any calendar conflict named |
| Customer replying about an overdue invoice | needs-you (invoice chasing is coming in a later release) | Flag it; no collection reply is drafted |
| Contract, NDA, MSA, or agreement attached | needs-you (contract review is coming in a later release) | Flag it for the owner; no redline |

Anything that does not match stays here and gets triaged normally.

**An inquiry reply is still draft-only.** Nothing here sends on its own; a reply that starts life in this inbox waits for the owner's yes like every other draft here. The handoff moves the qualifying work, not the send permission.

**Nor does a scheduling thread ever leave the owner's hands.** This skill drafts the reply; it never books, accepts, or declines anything. Say the reply is drafted and waiting.

---

## How to spot each one

**A bill, not a receipt.** A bill asks for money that has not moved yet: an invoice number, a due date, an amount owed, payment instructions. A receipt confirms money that already moved. Receipts are handled and filed; bills go to needs-you with the due date pulled out. Getting this backwards means a bill sits in the archive until it goes past due.

**A real inquiry, not a sales pitch.** An inquiry describes their own problem and asks whether the owner can help. A pitch describes the sender's product. Pitches are handled and never surfaced. When it is genuinely ambiguous, treat it as an inquiry — the cost of one wasted qualification is far below the cost of one missed customer.

**A scheduling thread, not a mention of a date.** "Can we do Thursday at 2" is scheduling. "We finished Thursday" is not.

---

## What to pass along

Hand over the whole thread, not a summary. The receiving skill needs the attachment, the sender's address, the full history, and the timestamps. A summary loses the invoice PDF, which the owner will need.

**In pasted mode, hand over the full pasted text exactly as the owner gave it**, and say plainly that the attachment is not there:

```
Ferguson bill → needs you. I only have the pasted text, not the PDF, so
the line items will have to come from what's below or from the file itself.
```

Also pass what you already know, so the work is not repeated:

- Which bucket you had put it in
- Any deadline or amount you extracted
- Whether anyone at the business already replied

---

## When the receiving skill is not installed

Say so by name and keep the item. Do not drop it and do not pretend it was handled.

```
2 vendor bills came in (Ferguson USD 1,847, Sid Harvey USD 612). Bill processing isn't
in this release, so I've left them in "needs you" with the due dates pulled out.
```

The owner can then decide whether to install it or handle the bills by hand. Either way nothing is lost, which is the promise this skill is making.

---

## Worked example — Okonkwo Mechanical

Ray's Tuesday triage produced three handoffs:

- **Ferguson Enterprises invoice #88214, USD 1,847, net 30, due Aug 12** → needs you. Full PDF kept, nothing coded.
- **Sid Harvey statement, USD 612** → needs you. Statement, not an invoice, so flagged for Ray to confirm it matches the two bills already paid.
- **Web form — Alamo Heights homeowner, "AC not cooling upstairs"** → reply drafted here. Arrived 11:40 pm, unanswered, so it is the oldest thing in the queue by response-time.

All three appeared in the digest under "handed off," with one line each. Ray knows where they went.
