# Traceability Gap Report — RDA Cameo Model

> **Status: TEMPLATE — no defects recorded yet.**
> Fill this in after the deliberate-defect exercise: once the Cameo model
> passes the full [model consistency checklist](../docs/model_consistency_checklist.md),
> deliberately introduce 2–3 traceability defects, re-run the checklist to
> find them, fix them, and document each one below.

## How to fill this in

- One **Defect** section per defect (copy the block; number sequentially DEF-01, DEF-02, …).
- Write the *how it was found* section against the checklist item that caught it — if no checklist item caught it, that's a checklist gap: fix the checklist too and say so.
- Evidence = Cameo screenshots (containment tree, relation map, or validation results) exported to `../diagrams/gap-evidence/`, named `DEF-XX-before.png` / `DEF-XX-after.png`. RTM rows count as evidence for allocation mismatches.
- Keep it honest: record what you actually did, including wrong turns. The debugging narrative is the interview artifact, not the polish.

## Summary table

| ID | Defect (one line) | Type | Found by (checklist item) | Status |
|----|-------------------|------|---------------------------|--------|
| DEF-01 | | | | |
| DEF-02 | | | | |
| DEF-03 | | | | |

*Type: dangling satisfy · missing satisfy · dangling verify · allocation mismatch · BDD/IBD disagreement · derivation gap · other (name it).*

---

## DEF-01

### Defect found

<!-- What is wrong, precisely. Name the requirement ID, the link type, and the
model elements involved. "REQ-0XX's satisfy link points at a block that was
renamed" — not "traceability was broken". -->

### How it was found

<!-- Which checklist item (or Cameo validation rule, or RTM cross-check)
surfaced it. What the failing signal actually looked like — validation error
text, empty relation map cell, RTM row that wouldn't reconcile. -->

### Root cause

<!-- Why the defect existed — the modeling action that created it (rename
without refactor, copy-paste of a requirement element, deleting a block
without checking its relations). For deliberately seeded defects, state what
you seeded AND whether the find matched what you expected to find. -->

### Fix applied

<!-- The exact change in Cameo: relation re-targeted, link recreated, element
renamed, RTM row corrected. Include the RTM.xlsx row update if the fix
touched allocation or evidence columns. -->

### Evidence (before / after)

| | Artifact |
|---|---|
| Before | `../diagrams/gap-evidence/DEF-01-before.png` |
| After | `../diagrams/gap-evidence/DEF-01-after.png` |

<!-- Add RTM row references or Cameo validation output as extra rows if used. -->

---

## DEF-02

### Defect found

### How it was found

### Root cause

### Fix applied

### Evidence (before / after)

| | Artifact |
|---|---|
| Before | `../diagrams/gap-evidence/DEF-02-before.png` |
| After | `../diagrams/gap-evidence/DEF-02-after.png` |

---

## DEF-03

### Defect found

### How it was found

### Root cause

### Fix applied

### Evidence (before / after)

| | Artifact |
|---|---|
| Before | `../diagrams/gap-evidence/DEF-03-before.png` |
| After | `../diagrams/gap-evidence/DEF-03-after.png` |

---

## Lessons / checklist feedback

<!-- After all defects are closed: which checks earned their keep, which
defect nearly slipped through, and any checklist items added or sharpened as
a result. This section is what turns the exercise into an interview story. -->
