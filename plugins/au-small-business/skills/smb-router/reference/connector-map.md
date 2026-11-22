# Connector Map

Required and optional connectors per skill, plus each skill's zero-connector fallback. The router uses this to avoid recommending something that will partially fail, and to offer the fallback path instead.

**The lists below are the tested paths, not a wall.** When the owner wants a skill to use a tool that is not listed for it, route to `build-connector` first — it checks the connector directory, then connects through Zapier. Once the connection exists, the tool joins that skill like any other optional connector, with the same approval gates.

Every skill works with zero connectors. "Required" below means required for the *connected* path — the fallback column is always available.

**Call shapes.** Parameter shapes that connectors require and tool descriptions do not make obvious are collected in [`../../../shared/connector-call-shapes.md`](../../../shared/connector-call-shapes.md); a skill reads the row for a connector before its first call to it.

**One product, possibly two entries.** The owner's own connector and the plugin's manifest registration of it (`small-business:<name>`) count as one; a gate opens if either is authorized (`../../../shared/connector-neutrality.md`, "One connector, two registrations").

**Gates are categories, not vendors.** Where a row says "a ledger," any of MYOB, NetSuite, QuickBooks, Xero, or Zoho Books opens the gate; "a payments connector" is any of PayPal, Square, or Stripe; "a CRM" is any of HubSpot, Monday.com, Salesforce, or Zoho CRM (Salesforce is owner-added as a custom connector, not in the manifest); "a storefront" is either of Shopify or Square (the connectors that hold orders and stock); "Mail" is either of Gmail or Microsoft 365; "a file store" is either of Google Drive or Microsoft 365 (Microsoft 365 is one connector covering both of those categories, and is owner-added as a custom connector, not in the manifest); and none ranks above another (`../../../shared/connector-neutrality.md`). Vendor lists are alphabetical. Capability limits that matter to a gate are in the footnotes under each table, stated as what the connector holds, not as a ranking.

---

## Run the business

| Skill | Required | Optional | Zero-connector fallback |
|---|---|---|---|
| `report-builder` | any one data source | Expensify, HubSpot, MYOB, NetSuite, PayPal, QuickBooks, Ramp, Shopify, Square, Stripe, Xero, Zoho Books | CSV/XLSX upload — fully functional |
| `business-pulse` | none | Calendar, DocuSign, Expensify, Gmail or M365, Gusto, HubSpot, MYOB, NetSuite, PayPal, QuickBooks, Ramp, RingEx Chat, Shopify, Slack, Stripe, TikTok Ads, Xero, Zoho Books, Zoho Desk | builds from whatever exists, or pasted data |
| `inbox-manager` | Gmail or M365 | Slack | pasted/forwarded email text |

Ledger capability notes (what each holds, per its own reference files):
- **MYOB** — P&L, AR and AP balances, sales totals, payment terms. No bank or cash balances, no vendor or payee detail, no customer email addresses. A skill that needs those asks the owner or uses another source, and says so.
- **NetSuite** — full ledger via reports and SuiteQL. Common at the larger end of the segment.
- **QuickBooks** — full ledger, with the report traps in `../../../shared/quickbooks-report-traps.md`.
- Two ledgers connected: read both, one named as the source of record for totals, never summed.

Storefront and point-of-sale capability notes (what each holds, per its own reference files; the category is defined in `../../../shared/connector-neutrality.md`):
- **Square** — orders with line items, catalog with images, inventory counts, payments, and payouts; merchant record carries country and currency. Payments list one location per call, so skills iterate locations. Payouts can be structurally absent on a production account.
- A storefront alone satisfies any gate written as "a CRM, a payments connector, or a storefront": order history is who bought what and when.
- Storefront and payments connectors both connected: an order and its settlement are one sale. Revenue comes from the one the owner names as source of record; the other supplies timing, fees, or stock.

## Grow the business

| Skill | Required | Optional | Zero-connector fallback |
|---|---|---|---|
| `lead-triage` | HubSpot | Apollo, Calendar, Clay, Gmail or M365 | pasted/uploaded lead list |
| `crm-autopilot` | a CRM (HubSpot, Monday.com, Salesforce, or Zoho CRM) | Calendar, Notion, RingEx Chat, Trello, Zoom | built-in spreadsheet CRM |
| `growth-pulse` | HubSpot + one revenue source | Mailchimp, PayPal, Shopify, Square, Stripe, TikTok Ads | CSV exports |

## Build & meta

| Skill | Required | Optional | Fallback |
|---|---|---|---|
| `build-agent` | none | whatever it builds against | native |
| `build-connector` | none | Emergent, Zapier | it builds the fallback |
| `smb-onboard` | none | all | interview-based, recommends what to connect |
| `brand-style` | none | website via WebFetch | plain-words brand description; house default on skip |

## Commands (11 folders + 1 in-skill chain)

The command folders in this release are listed below.

Commands inherit the requirements of the skills they chain. The lead skill's requirement decides whether the command can start; optional legs degrade per skill.

| Command | Gate to start |
|---|---|
| `/report-pack` | any one data connector, or CSV |
| `/monday-brief` | none — degrades gracefully |
