# AI Council of Agents

Governance and orchestration layer for ALC and Sisu Coaching & Consulting.

This repo documents the **AI Council of Agents** — the meta-layer that builds, governs, and continuously improves the ALC / Sisu agent infrastructure. Business agent operations live in the `alc-agent-ops` repo.

## Council Members

| Role | Functional Name | Agent | Responsibility |
|---|---|---|---|
| Orchestrator | Orchestrator | Professor X (PX) | Orchestration, routing, gate authority |
| Implementer | Infrastructure | Architect | Infra implementation, fleet wiring, A2A mesh |

## Structure

```
ai-council/
  /docs/
    council-charter.md       ← Purpose, members, decision authority
    routing-playbook.md      ← Work routing: DUAL_ASSIGN, O1 pattern
    lessons-learned.md       ← L-001 through L-007 (infrastructure lessons)
    signoff-ledger.md        ← Plan sign-off history
```

## Purpose

The AI Council of Agents:
- **Builds** and governs the agent infrastructure
- **Does not operate within** the business agent fleet
- Captures every lesson from infrastructure builds and applies them to its own standards
- Holds decision authority on Phase gates (Phase 0 → Phase 1 → Phase 2)

## Related Repos

- [`alc-agent-ops`](https://github.com/Cybercoon/alc-agent-ops) — ALC/Sisu business agent fleet
