# PetersonMBSE-Demo

MBSE portfolio project: a small, unclassified, plausible **Route Deconfliction
Advisory (RDA)** subsystem for a mission planning tool, modeled in SysML with
Cameo Systems Modeler. Built as hands-on preparation for a Systems Engineer
(MBSE) interview.

## What this is

The RDA subsystem takes a candidate route, checks it against all active routes
and airspace constraints, and issues severity-classified deconfliction
advisories with recommended modifications — advisory only, the operator always
holds route authority. Fourteen "shall" requirements
([`requirements/requirements.yaml`](requirements/requirements.yaml)) drive the
model: functional, timing, capacity, interface, data, safety/operator-override,
and availability.

## What's hand-built vs. generated — read this

The SysML model is the point of this project, and it is **built by hand in
Cameo**:

- the BDD, IBD, Requirements, Activity, and Parametric diagrams (`diagrams/`),
- the model file itself (`model/*.mdzip`),
- the RTM's Model Element(s), Test/Evidence, Status, and Owner columns
  (`traceability/RTM.xlsx`),
- and the traceability gap report findings.

That's deliberate: requirement-to-element satisfy/verify linking, BDD/IBD
consistency, and defect hunting are the skills being practiced — not something
an AI assistant generated. Claude Code produced the scaffolding *around* the
model: requirements text, the RTM skeleton, document outlines, and this repo
structure.

## Repo structure

```
peterson-mbse-demo/
├── model/                  Cameo project file (.mdzip) — hand-built
├── diagrams/               PNG exports from Cameo — hand-built
│   └── gap-evidence/       before/after screenshots for the gap report
├── requirements/
│   └── requirements.yaml   14 shall statements w/ rationale, verification
│                           method, success criteria (allocated_block filled
│                           by hand from the BDD)
├── traceability/
│   ├── RTM.xlsx            requirements traceability matrix — IDs/source/
│   │                       verification pre-filled, links filled by hand
│   └── traceability_gap_report.md   deliberate-defect exercise writeup
├── docs/
│   ├── LCSP_outline.md     portfolio-scope DoD LCSP approximation
│   └── model_consistency_checklist.md   pre-completion model review gate
└── README.md
```

## Workflow

1. **Author requirements** — 14 singular, testable shall statements with
   measurable success criteria. ✅
2. **Scaffold artifacts** — RTM skeleton, LCSP outline, consistency checklist,
   gap report template. ✅
3. **Model in Cameo** — build BDD → IBD → Requirements diagram → Activity →
   Parametric from the requirements baseline; create satisfy/verify links;
   fill RTM and `allocated_block` as the model grows.
4. **Consistency pass** — run the full
   [model consistency checklist](docs/model_consistency_checklist.md).
5. **Deliberate-defect exercise** — seed 2–3 traceability defects, rediscover
   them with the checklist, fix them, and write up
   [the gap report](traceability/traceability_gap_report.md) with before/after
   evidence. This is the artifact that shows traceability skill rather than
   claiming it.

## Scope honesty

Everything here is unclassified and invented for practice. Separation minima,
timing budgets, and availability targets are plausible-sounding engineering
values chosen for testability, not sourced from any real program. The LCSP
outline says the same thing about itself, louder.
