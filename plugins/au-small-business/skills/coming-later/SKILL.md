---
name: coming-later
description: "Handles requests and questions about work this release of Small Business (Australia) doesn't do yet, including quick what-is questions such as \"what's the super rate?\" or \"when is BAS due?\". Use for anything about BAS, GST, tax, a tax set-aside, PAYG, TPAR, payroll, pay runs, timesheets, super or the super guarantee rate, STP, award rates, casual loading or leave entitlements, overdue invoices or who owes money, paying bills or suppliers, cash flow forecasts or runway, month-end close or reconciliation, stock reorders, enquiry replies, grants or tenders, offer letters, reviewing or drafting a contract or agreement, proposals, quotes or statements of work, hiring, refunds, reviews, cold outreach, social posts, ads or SEO. Says it's coming in a later release, gives no rates, thresholds or due dates, and offers what the plugin can do now."
---

# Coming in a later release

> **Personal data comes first.** Never reproduce a tax file number, Medicare number, super member number, full bank account number or BSB, card number, date of birth, home address, or driver licence, passport or visa number in any output: chat, page, file, CRM note or draft email. That holds even when the owner pasted it in. Leave it out, say once what was left out and why, and suggest the person enter it in the payroll system or send it through a secure channel. Full rule: `../../shared/personal-data.md`.

Small Business (Australia) is released in stages. Each release includes only
the skills that have been adapted for Australian rules and, where they touch
tax, payroll, employment or the law, checked by a registered adviser. The
request in front of you belongs to a skill that isn't in this release yet.

## What to do

1. **Say it plainly, in one or two sentences.** Name the job ("BAS
   preparation", "payroll", "chasing overdue invoices") and say it's coming in
   a later release of this plugin, once it has been adapted and checked for
   Australian rules.
2. **Offer what this release can do instead**, from the "Available now" list
   below, when something there genuinely helps. Pick at most two. Examples:
   - BAS, tax or cash worries: `business-pulse` gives a snapshot of cash,
     sales and pipeline from the connected books.
   - Wanting the same numbers every month: `report-builder` can set up a
     report from the books.
   - Overdue invoices or bills: `inbox-manager` can find and rank the related
     emails; it won't draft payment demands.
   - A task done by hand every week: `build-agent`.
3. **For tax, BAS, payroll, super or employment questions**, suggest the
   owner's registered BAS or tax agent, or the Fair Work Ombudsman for award
   and employment questions.
4. **Stop there.** Don't start the held job another way yourself.
5. **If the owner still wants help**, that's their call: Claude can help with
   anything they ask. Say once, plainly, that this is general help from
   Claude, not part of Small Business (Australia), and not checked for
   Australian rules (for example GST and ABN on a quote, or consumer and
   contract law). Then help. Even then, state no tax, payroll, employment or
   legal rate, threshold or due date (see below).

## Never, while a skill is held

- **Never start the held work yourself** (unless the owner asks for general help, step 5), from general knowledge or by
  calling a connector: no BAS or GST figures, no tax estimate or set-aside
  amount, no pay run, payroll preview or super calculation, no reminder or
  demand to a customer, no payment run, no cash forecast, no offer letter or
  contract clauses.
- **Never state a rate, threshold, due date or legal rule from memory**: not
  a BAS due date, a super rate, an award rate, a tax rate or a GST threshold.
  These change and must come from a dated source, which the held skill will
  carry when it's released.
- **Never use a US payroll or tax service** (for example Gusto or QuickBooks
  Payroll's US payroll tools) for an Australian business.
- **Never hand off to a held skill** or tell the owner to run one.

A general explanation of what something is ("what is a BAS?") is fine, as
long as it carries no figures or dates and ends by pointing to their agent.

## Available now

- `brand-style`: Sets and updates the owner's brand look and output preferences, which every page and document the plugin produces then follows automatically.
- `build-agent`: Turns a task the owner keeps doing by hand into a named, reusable skill they can trigger by name or put on a schedule.
- `build-connector`: Gets Claude talking to a tool nobody built an official connector for.
- `business-pulse`: Produces a one-page cross-functional business snapshot for SMB owners — cash position (the ledger: MYOB, NetSuite, QuickBooks, Xero, or Zoho Books), sales trend (PayPal/Square/Stripe), pipeline movement (HubSpot), this week's commitments (Calendar), urgent watch-list items (Gmail or M365, Slack), and the single most important thing needing attention today.
- `crm-autopilot`: Keeps the CRM current without the owner ever opening it.
- `growth-pulse`: Answers one question for an SMB owner — is the growth engine actually working?
- `inbox-manager`: Turns a full inbox into a short, ranked list of what actually needs the owner.
- `lead-triage`: Scores inbound HubSpot leads by engagement signals, company fit, and urgency markers, ranks the ones worth a call today with talking points, drafts the follow-ups, and proposes calendar times for the owner to book.
- `monday-brief`: Runs the owner's Monday morning briefing as a two-link chain — business-pulse for the cross-connector snapshot of cash, sales, and pipeline, and report-builder for any saved KPI reports the owner has already defined — then reads the week ahead straight from Calendar and mail and merges all three parts into a single one-page Monday document, delivered per the owner's stored output preference.
- `report-builder`: Turns a plain-English description of a recurring report into a real, repeatable report — defines the metrics, pulls them from whatever data sources are connected, delivers a chat summary plus an XLSX workbook, and saves the definition so the same report reruns on demand or on a schedule.
- `report-pack`: Delivers the owner's custom recurring report pack on a set cadence — runs the saved report definition from report-builder, wraps it in a business-pulse snapshot so the numbers have context, and hands over one chat summary plus the workbook.
- `smb-onboard`: Claude as the trainer.
- `smb-router`: The front door to the Small Business plugin.

## When another skill hands work here

Other skills in this plugin send work to `coming-later` when it belongs to
a skill that isn't released yet: for example, bills found in the inbox, or a
payroll or tax question during onboarding. Treat that the same way: say the
job is coming in a later release, carry on with the rest of the task, and
don't do the held part.
