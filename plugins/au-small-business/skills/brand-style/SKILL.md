---
name: brand-style
description: >
  Sets and updates the owner's brand look and output preferences, which every
  page and document the plugin produces then follows automatically. Captures
  the brand from a pasted website link or a plain-words description — never a
  hex code, color picker, or upload — previews it on a sample page, asks how
  they want their outputs delivered (visual artifacts, Word docs, markdown, Notion pages,
  Canva Docs, or best-for-the-skill), and saves both to the business profile. Runs inside
  smb-onboard on first setup and stands alone forever after. Use when the
  owner says "update my brand," "we rebranded," "change my colors," "make the
  reports match our new look," "change how you give me reports," "I want Word
  docs instead," or anything about the look or format of what the plugin
  hands them.
allowed-tools: Read, WebFetch
---

<!-- Modified from Anthropic's Small Business plugin (Apache-2.0) for Australian use. See NOTICE. -->

# Brand Style

> **Personal data comes first.** Never reproduce a tax file number, Medicare number, super member number, full bank account number or BSB, card number, date of birth, home address, or driver licence, passport or visa number in any output: chat, page, file, CRM note or draft email. That holds even when the owner pasted it in. Leave it out, say once what was left out and why, and suggest the person enter it in the payroll system or send it through a secure channel. Full rule: `../../shared/personal-data.md`.

> **Held topics: no figures.** Tax, GST, BAS, payroll, super, award and other employment rules, and legal advice are not in this release. Don't state a rate, threshold or due date for them, even in passing (for example a casual loading in a draft email): leave a placeholder, say it's coming in a later release, and point to the owner's registered BAS or tax agent or the Fair Work Ombudsman.

One place the owner controls how everything looks and how everything is
delivered. Set once during onboarding, changed any time after with one
sentence.

## Step 1 — Show what is set now

Read the `## Business context` block. If Brand colors, Logo, or Output
preference exist, play them back in plain words first: "Right now your pages
use a deep green and cream with your leaf logo, and you get visual pages.
What's changing?" An owner updating one thing should not re-answer the rest.

If nothing is stored yet (first run, usually inside `smb-onboard`), skip
straight to capture.

## Step 2 — Capture the brand, frictionlessly

Two paths, both costing the owner almost nothing:

- **A website link.** Fetch the site (WebFetch) and pull the logo URL,
  primary brand colors (from the CSS, theme, or social-preview image), and
  tagline. The owner does nothing but paste the link. Guidance in
  [`../smb-onboard/reference/website-research.md`](../smb-onboard/reference/website-research.md).
- **A plain-words description.** "Forest green and cream," "navy and warm
  gray," "like a modern law firm." Translate the words to real colors
  yourself.

**Never ask for hex codes, color pickers, or file uploads.** Branding costs
one pasted link or one spoken sentence, nothing more. "Skip" is always an
answer and means the clean house default.

## Step 3 — Preview before saving

Render a small sample page as an HTML artifact in the house style
(`../../shared/artifact-style.md`) with the candidate brand applied — a
title, one stat tile, a short table, a status pill — so the owner sees the
look on real components, not a color swatch. Ask one question: "Match?"

If they adjust ("darker green," "less cream"), apply and re-preview. This
loop is cheap; a wrong brand on every future page is not.

## Step 4 — Ask how outputs should arrive

The six-way choice, as a multiple choice (skip if the owner only came to
change colors and the preference is already stored):

1. **Visual artifacts** — styled pages viewed right here (the default)
2. **Word docs** — DOCX files to download
3. **Markdown** — plain .md files to download
4. **Notion** — pages created in their Notion workspace (needs the Notion connector; ask where in the workspace they should land)
5. **Canva** — Canva Docs created in their Canva account (needs the Canva connector; if it is connected, run `list-brand-kits` and ask once which brand kit to apply, or none; if not, the first skill that delivers to Canva asks)
6. **Best for the skill** — each skill picks what fits its job

Store the answer verbatim as one of: `visual artifacts`, `docx`, `md`,
`notion`, `canva`, `best for skill`. If they pick Notion or Canva and that
connector is not connected, store it anyway, say deliverables fall back to
visual artifacts until it is connected, and offer to help connect it.

## Step 5 — Save, with approval

Show what will be stored — Website, Brand colors, Logo, Output preference,
and Canva brand kit (name and id) when the preference is Canva — and wait
for the yes. Then update only those fields in the
`## Business context` block, using the exact field names in
[`../smb-onboard/reference/onboard-checklist.md`](../smb-onboard/reference/onboard-checklist.md).
Never touch the other fields, and never overwrite silently.

Close with the effect, not the mechanics: "Done — every page and document
from here on uses the new look."

## What not to do

- **Do not ask for hex codes, pickers, or uploads.** One link or one
  sentence, always.
- **Do not re-run the whole interview.** This skill changes look and
  delivery, nothing else — an owner who says "update my brand" is not
  signing up for onboarding again.
- **Do not save without the preview and the yes.** A brand applied to every
  future page deserves one confirmation.
- **Do not restyle old deliverables.** The change applies from now on;
  never claim past documents were updated.

## After the update

One line on what changed. The natural next step is seeing it live: offer
"Monday brief" (`/monday-brief`) or "how's the business doing?"
(`business-pulse`) so the first branded page arrives immediately. Never more
than three offers; never repeat one declined this session.
