# Life Cycle Sustainment Plan (LCSP) Outline — Route Deconfliction Advisory (RDA) Subsystem

> **SCOPE DISCLAIMER — READ FIRST**
> This is a **portfolio-project-scope approximation** of a DoD LCSP, written for
> MBSE interview preparation. It follows the standard LCSP section structure and
> applies each section to the RDA subsystem in brief, but it is **not** a
> program-accurate LCSP: no real program data, no approved funding lines, no
> coordinated stakeholder inputs, and no milestone-driven annexes. A real LCSP
> is a living program document owned by the Program Manager and coordinated
> with the product support ecosystem.

---

## 1. Introduction / Sustainment Overview

The RDA subsystem is a software-only component of a larger mission planning
tool, hosted on standard ground infrastructure with no unique hardware of its
own. Sustainment scope is therefore software maintenance, data feed
subscriptions (airspace constraint sources), and the underlying COTS host
environment — there is no organic depot or peculiar support equipment tail.

## 2. Sustainment Strategy

The strategy is contractor-supported software sustainment transitioning toward
government-led maintenance as the codebase stabilizes, consistent with a
non-flight-critical ground software item. Releases follow a periodic block
update cycle (nominally semi-annual) with out-of-cycle patches reserved for
defects that break the operator-override or audit-trail requirements
(REQ-012, REQ-013).

## 3. Supportability Requirements

Supportability derives directly from the requirements set: 99.5% operational
availability (REQ-014), 30-day audit data retention (REQ-010), and bounded
re-evaluation timelines after airspace changes (REQ-005) size the hosting,
monitoring, and backup posture. These flow down to the host environment as
uptime, storage, and failover requirements rather than to any RDA-unique
hardware.

## 4. Maintenance Concept

Two-level software maintenance: field-level (operator-site) actions are
limited to service restart, log collection, and constraint-feed
reconfiguration; all code changes occur at the software support activity via
the block release process. No intermediate level exists — a deliberate
simplification appropriate to a single-baseline ground software product.

## 5. Obsolescence / DMSMS Planning

DMSMS exposure is concentrated in the COTS stack: host OS, container runtime,
and the external airspace data provider's interface (ICD-RDA-002). Mitigation
is an annually refreshed technology roadmap, pinned-and-tracked dependency
manifests, and a contractual notification clause with the data provider for
interface deprecations, with a minimum two-release overlap window before any
interface retirement.

## 6. Funding / Resourcing Summary

Sustainment funding covers a small software sustainment team (nominally 2–3
FTE), recurring data subscription fees, and host infrastructure costs; the
dominant cost driver is the sustainment team, not infrastructure. Portfolio
scope: no actual budget figures, appropriation categories, or POM positions
are represented here — a real LCSP would tie each line to a funded program
element.

## 7. Sustainment Metrics

Primary metrics: operational availability (Ao, target ≥ 99.5% per REQ-014),
mean time to restore service, defect escape rate per block release, and
advisory-latency conformance (p95 ≤ 2.0 s per REQ-004) tracked as a leading
indicator of degradation. Metrics are reviewed at each block release decision
and feed the strategy re-evaluation in Section 2.

---

*Traceability note: sections above cite requirement IDs from
[`requirements/requirements.yaml`](../requirements/requirements.yaml) so
sustainment claims stay anchored to the requirements baseline rather than
free-floating prose.*
