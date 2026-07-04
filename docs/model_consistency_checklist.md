# Model Consistency Checklist — RDA Cameo Model

Run this manually against the Cameo model before calling it done. Every check
is pass/fail — no partial credit. Record failures as candidate entries for
`traceability/traceability_gap_report.md`.

**How to use:** work top to bottom. Sections 1–3 are the traceability core
(where the deliberate defects for the gap report will live). Sections 4–6
catch structural rot that RTM-level review misses.

---

## 1. Requirements coverage

- [ ] Every requirement in `requirements/requirements.yaml` (REQ-001 … REQ-014) exists as a Requirement element in the model, with matching ID and text.
- [ ] Requirement text in the model matches the YAML `shall_statement` verbatim — no silent paraphrasing drift.
- [ ] Every Requirement element has at least one **satisfy** link from a model element.
- [ ] No requirement is satisfied *only* by a package or diagram — satisfy sources must be blocks, parts, or behaviors.
- [ ] Every requirement's `allocated_block` in the YAML matches the block that actually satisfies it in the model.

## 2. Link validity

- [ ] Every **satisfy** link points to an existing model element — no dangling references to deleted or renamed blocks.
- [ ] Every **verify** link points to a real test case element that exists in the model.
- [ ] Every test case referenced by a verify link corresponds to a row entry in `traceability/RTM.xlsx` (Test/Evidence Artifact column).
- [ ] Verification method implied by each test case matches the `verification_method` in the YAML (e.g., REQ-014 is Analysis — it should not have a Test-type verify link).
- [ ] No orphan Requirement elements: every requirement participates in at least one satisfy AND one verify relationship.
- [ ] No orphan test cases: every test case in the model verifies at least one requirement.

## 3. Derivation and refinement

- [ ] Requirements that reference other requirements in their text (REQ-002→001, REQ-003→001/008, REQ-006→004/005, REQ-011→REQ-009 message, REQ-013→012) have corresponding **deriveReqt** or **refine** links in the model.
- [ ] No circular derive chains.

## 4. BDD / IBD agreement

- [ ] Every block on the IBD appears on the BDD — no parts typed by blocks that don't exist in the block hierarchy.
- [ ] For every connector on the IBD, the ports at both ends exist on the corresponding blocks in the BDD, with matching types.
- [ ] Port directions are consistent: every out-flow on one end has a matching in-flow on the other; no two outputs wired together.
- [ ] Item flows on IBD connectors are typed (route data, constraint data, advisory message) — no untyped connectors on interfaces that carry REQ-007/008/009 traffic.
- [ ] Interface blocks referenced by proxy ports are defined once and reused — no duplicate interface definitions with divergent contents.
- [ ] External actors (mission planning client, airspace data provider) appear at the subsystem boundary and every boundary crossing corresponds to an ICD named in the requirements (ICD-RDA-001, ICD-RDA-002).

## 5. Behavioral consistency

- [ ] Every activity diagram action that sends or receives data across the subsystem boundary corresponds to a port on the IBD.
- [ ] The operator accept/reject/override flow (REQ-012, REQ-013) appears in a behavior diagram, and the decision node's outgoing edges cover all three outcomes plus timeout/no-response if modeled.
- [ ] Activity parameters match the operations/receptions on the owning block — no free-floating behaviors unattached to any block.

## 6. Parametric consistency

- [ ] Every parametric constraint block has all parameters bound — no unbound constraint parameters.
- [ ] Constraint values allocated across sub-blocks sum correctly to the system-level value (e.g., if the 2.0 s latency budget of REQ-004 is split across ingest/detect/publish, the sub-budgets sum to ≤ 2.0 s).
- [ ] Units are consistent on both ends of every binding connector (seconds vs milliseconds, NM vs km).
- [ ] Each parametric diagram traces to the requirement whose threshold it models (REQ-004, REQ-005, REQ-014) via satisfy or refine.

## 7. Hygiene

- [ ] No elements with default names (`Block1`, `Activity2`, `unnamed`).
- [ ] Every diagram has a completed description field stating what question the diagram answers.
- [ ] Containment tree has no empty packages left over from restructuring.
- [ ] Model validates clean in Cameo's built-in validation suite (no unresolved profile errors).

---

*Checks in sections 1–2 are the ones the deliberate traceability defects
(gap report exercise) should target — break a satisfy link, dangle a verify
link, or mismatch an allocated block, then find them with this list.*
