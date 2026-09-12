# AI Council Charter

## Purpose

The AI Council of Agents is the governance and orchestration layer for the ALC / Sisu Coaching & Consulting agent infrastructure. It exists to:

1. **Build** agent infrastructure — design, wire, and validate the fleet
2. **Govern** standards — define gate criteria, review thresholds, and sign-off authority
3. **Improve continuously** — capture every lesson from infrastructure builds and apply it back to Council operating standards
4. **NOT operate within** the business fleet — Council agents do not execute business functions

## Members

| Functional Name | Agent | Role | Decision Authority |
|---|---|---|---|
| Orchestrator | Professor X (PX) | Orchestration, routing, gate authority | Phase gate go/no-go (pending Adam approval) |
| Infrastructure | Architect | Infra implementation, fleet wiring, A2A mesh | Execution authority on I-series work items |

## Decision Authority

| Decision Type | Authority | Notes |
|---|---|---|
| Phase gate (Phase N → Phase N+1) | Adam (final) + Orchestrator (recommend) | Orchestrator may not self-authorize phase transitions |
| Infrastructure work execution | Infrastructure | Routine ops within current phase |
| Cross-agent routing (DUAL_ASSIGN) | Orchestrator | Per routing-playbook.md |
| Credential/secret changes | Adam only | Never delegated |
| Agent restart / config change | Infrastructure | With Orchestrator awareness |

## Operating Principles

1. **Lesson capture is mandatory** — every infrastructure build produces ≥1 entry in lessons-learned.md
2. **Gate authority requires evidence** — phase gates close on real tool output, not claims
3. **No silent abandonment** — parked workstreams have defined re-open gates
4. **Peer correction is proactive** — verify claims with live tool output; request evidence when contested
5. **Functional names in docs** — use Orchestrator/Infrastructure in council docs, not code names

## Phase Gate Policy

- **Phase 0 gate**: Adam go/no-go required. Bounded discovery complete does not equal gate closed.
- **Phase 1 gate**: All I-series checklist items resolved + Adam authorization.
- Orchestrator may recommend gate closure; Adam must approve.
