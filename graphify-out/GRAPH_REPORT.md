# Graph Report - .  (2026-07-03)

## Corpus Check
- Corpus is ~2,236 words - fits in a single context window. You may not need a graph.

## Summary
- 50 nodes · 101 edges · 8 communities detected
- Extraction: 97% EXTRACTED · 3% INFERRED · 0% AMBIGUOUS · INFERRED: 3 edges (avg confidence: 0.68)
- Token cost: 6,200 input · 7,800 output

## Community Hubs (Navigation)
- [[_COMMUNITY_LCSP Sustainment Planning|LCSP Sustainment Planning]]
- [[_COMMUNITY_Requirements Baseline|Requirements Baseline]]
- [[_COMMUNITY_Gap Report & Defect Evidence|Gap Report & Defect Evidence]]
- [[_COMMUNITY_Consistency Checklist & RTM|Consistency Checklist & RTM]]
- [[_COMMUNITY_Interfaces & ICDs|Interfaces & ICDs]]
- [[_COMMUNITY_Cameo Hand-Built Model|Cameo Hand-Built Model]]
- [[_COMMUNITY_Operator Override & Audit|Operator Override & Audit]]
- [[_COMMUNITY_Deliberate-Defect Workflow|Deliberate-Defect Workflow]]

## God Nodes (most connected - your core abstractions)
1. `RDA Requirements Baseline (14 Shall Statements)` - 19 edges
2. `Model Consistency Checklist` - 12 edges
3. `Derivation and Refinement Checks` - 12 edges
4. `Traceability Gap Report` - 10 edges
5. `Life Cycle Sustainment Plan (LCSP) Outline` - 10 edges
6. `PetersonMBSE-Demo Project` - 6 edges
7. `BDD/IBD Agreement Checks` - 6 edges
8. `REQ-003 Recommended Route Modification` - 5 edges
9. `REQ-004 Advisory Latency 2.0 s p95` - 5 edges
10. `REQ-005 Re-evaluation Within 5.0 s` - 5 edges

## Surprising Connections (you probably didn't know these)
- `Model Consistency Checklist` --semantically_similar_to--> `Requirements Traceability Matrix (RTM.xlsx)`  [INFERRED] [semantically similar]
  docs/model_consistency_checklist.md → README.md
- `Five-Step Modeling Workflow` --cites--> `Model Consistency Checklist`  [EXTRACTED]
  README.md → docs/model_consistency_checklist.md
- `Scope Honesty Rationale` --rationale_for--> `RDA Requirements Baseline (14 Shall Statements)`  [EXTRACTED]
  README.md → requirements/requirements.yaml
- `Requirements Coverage Checks` --references--> `RDA Requirements Baseline (14 Shall Statements)`  [EXTRACTED]
  docs/model_consistency_checklist.md → requirements/requirements.yaml
- `PetersonMBSE-Demo Project` --cites--> `RDA Requirements Baseline (14 Shall Statements)`  [EXTRACTED]
  README.md → requirements/requirements.yaml

## Hyperedges (group relationships)
- **Deliberate-Defect Exercise Workflow** — readme_deliberate_defect_exercise, model_consistency_checklist_checklist, traceability_gap_report_gap_report, traceability_gap_report_gap_evidence [EXTRACTED 1.00]
- **Requirements-to-Model Traceability Chain** — requirements_requirements_baseline, readme_sysml_model, readme_rtm, model_consistency_checklist_checklist [INFERRED 0.85]
- **Sustainment-Driving Requirements** — lcsp_outline_lcsp, requirements_req_014, requirements_req_010, requirements_req_005, requirements_req_004 [EXTRACTED 1.00]

## Communities

### Community 0 - "LCSP Sustainment Planning"
Cohesion: 0.24
Nodes (11): Life Cycle Sustainment Plan (LCSP) Outline, Two-Level Software Maintenance Concept, No-Intermediate-Level Simplification Rationale, Portfolio-Scope Disclaimer, Supportability Requirements Flow-Down, Sustainment Metrics (Ao, MTTR, Latency Conformance), Parametric Consistency Checks, Scope Honesty Rationale (+3 more)

### Community 1 - "Requirements Baseline"
Cohesion: 0.49
Nodes (10): Derivation and Refinement Checks, REQ-001 Spatial Conflict Detection, REQ-002 Severity Classification, REQ-003 Recommended Route Modification, REQ-005 Re-evaluation Within 5.0 s, REQ-006 Capacity of 50 Active Routes, REQ-008 Constraint Ingest and Quarantine, REQ-009 Advisory Message Content (+2 more)

### Community 2 - "Gap Report & Defect Evidence"
Cohesion: 0.33
Nodes (7): Debugging Narrative as Interview Artifact, DEF-01 Defect Entry, DEF-02 Defect Entry, DEF-03 Defect Entry, Traceability Defect Taxonomy, Gap Evidence Before/After Screenshots, Traceability Gap Report

### Community 3 - "Consistency Checklist & RTM"
Cohesion: 0.47
Nodes (6): Model Consistency Checklist, Model Hygiene Checks, Link Validity Checks, Requirements Coverage Checks, PetersonMBSE-Demo Project, Requirements Traceability Matrix (RTM.xlsx)

### Community 4 - "Interfaces & ICDs"
Cohesion: 0.5
Nodes (5): Obsolescence / DMSMS Planning, BDD/IBD Agreement Checks, ICD-RDA-001 Route-Submission Interface Definition, ICD-RDA-002 Constraint-Ingest Interface Definition, REQ-007 Route-Submission Interface

### Community 5 - "Cameo Hand-Built Model"
Cohesion: 0.5
Nodes (4): Cameo Systems Modeler, Hand-Built vs Generated Rationale, Route Deconfliction Advisory (RDA) Subsystem, Hand-Built SysML Model

### Community 6 - "Operator Override & Audit"
Cohesion: 0.83
Nodes (4): Sustainment Strategy (Block Update Cycle), Behavioral Consistency Checks, REQ-012 Operator Acceptance Required, REQ-013 Operator Action Audit Record

### Community 7 - "Deliberate-Defect Workflow"
Cohesion: 0.67
Nodes (3): Sections 1-2 Defect Targeting Rationale, Deliberate-Defect Exercise, Five-Step Modeling Workflow

## Knowledge Gaps
- **9 isolated node(s):** `Cameo Systems Modeler`, `Hand-Built vs Generated Rationale`, `DEF-02 Defect Entry`, `DEF-03 Defect Entry`, `Traceability Defect Taxonomy` (+4 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `RDA Requirements Baseline (14 Shall Statements)` connect `Requirements Baseline` to `LCSP Sustainment Planning`, `Consistency Checklist & RTM`, `Interfaces & ICDs`, `Cameo Hand-Built Model`, `Operator Override & Audit`?**
  _High betweenness centrality (0.329) - this node is a cross-community bridge._
- **Why does `Model Consistency Checklist` connect `Consistency Checklist & RTM` to `LCSP Sustainment Planning`, `Requirements Baseline`, `Gap Report & Defect Evidence`, `Interfaces & ICDs`, `Operator Override & Audit`, `Deliberate-Defect Workflow`?**
  _High betweenness centrality (0.275) - this node is a cross-community bridge._
- **Why does `Traceability Gap Report` connect `Gap Report & Defect Evidence` to `Consistency Checklist & RTM`, `Deliberate-Defect Workflow`?**
  _High betweenness centrality (0.253) - this node is a cross-community bridge._
- **What connects `Cameo Systems Modeler`, `Hand-Built vs Generated Rationale`, `DEF-02 Defect Entry` to the rest of the system?**
  _9 weakly-connected nodes found - possible documentation gaps or missing edges._