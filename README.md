# aw-abetworks-history

![CI](https://github.com/coding4vinayak/aw-abetworks-history/actions/workflows/ci.yml/badge.svg)


The campaign ledger. One file, no code.

`abetworks-improvements.txt` records 9251 lines of engineering decisions across the
Abetworks product family — 63 top-level sections (§8.1 through §8.63) plus their
subsections, each naming which apps the decision touched. It's the audit trail for
the fixes and guards in every app's `tests/unit/` tree: when a future reader asks
"why does this file look like this, and what breaks if I change it," the answer
lives here rather than in a commit message.

The file is a plain `.txt`, not `.md`, on purpose. It's not structured prose — the
`8.14.2` numbering is load-bearing, cross-references inside the text use those
numbers, and the campaign grew it line-by-line in a text editor for months before
this repo existed.

## Why this is a separate repo

The 6 apps that make up the Abetworks family (`abetagent`, `abetanalytics`,
`abetapi`, `abetflow`, `leadgenius`, `leadworks`) are each their own product. 13 of
the 63 sections name one app; 50 name two or more. Duplicating a cross-app section
into each app's `docs/` would mean three copies of the same paragraph drifting
apart, which is exactly the failure mode the campaign was fighting.

So the ledger lives whole, here. Each app's `docs/LEDGER-INDEX.md` names which §§
apply to it and points into this file. That's a pointer, not a copy.

## Reading order

If you have a specific product in mind, open that product's repo and read its
`docs/LEDGER-INDEX.md` first — it lists the §§ relevant to that app. Come here for
the full narrative and the cross-app rationale.

If you want the arc of the campaign end to end, read §8.1 → §8.63 in order.

If you want the newest decisions first, read §8.55 → §8.63 — those are the last
sweep and cover egress policy (#32), outbound webhooks (#17), queue retention
(#64), fail-closed workspaceId claims (#43), and the ledger's own fragmentation
(§8.63).
