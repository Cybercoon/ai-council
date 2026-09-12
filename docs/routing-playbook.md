# Routing Playbook

How work gets routed within the AI Council and to the fleet.

## O1 Pattern (Orchestrator-First)

All non-trivial work is initiated by the Orchestrator (PX). Infrastructure receives assignments; does not self-initiate phase changes.

```
Adam → Orchestrator → [route to agent]
                    ↓
               Infrastructure (I-series infra work)
               Converter (CRM/delivery work)
               Researcher (prospect/discovery work)
```

## DUAL_ASSIGN Pattern

Used when a task has both an infra component and a business component, or requires independent review.

```yaml
op_id: <uuid>
primary: Infrastructure        # execution owner
reviewer_a: Orchestrator       # sign-off reviewer
adam_gate: required=<yes|no>   # whether Adam approval is needed
sla: <24h|48h>
```

Rules:
- Primary executes and reports
- Reviewer_a validates output (does not re-execute)
- Adam gate = yes → work is NOT complete until Adam approves
- Empty ack or silent timeout = failure; prefer a 3-line ack over silence

## Work ID Schema

| Prefix | Domain | Example |
|---|---|---|
| I- | Infra (Infrastructure-owned) | I-1, I-2, I-3 |
| px- | Orchestrator-initiated blockers | px-blockers-infra-resolve-02 |
| infra- | Infra-tracked items | infra-github-repo-01 |
| B- | Beast/Converter review items | B-v62-3 |

## A2A Reply Discipline

- Smoke/ping acks (`PONG`): exact required text only. No tools. No preface.
- Ownership acks: non-empty within A2A timeout. State: (1) primary locked, (2) REPORT_TO_TRAINER update status, (3) open blockers.
- Never claim alc-health / Mem0 / MCP success without real tool or status-file result in the same turn.

## Escalation Path

```
Agent timeout / blocker → Orchestrator notified immediately
Orchestrator cannot resolve → Adam (Telegram, direct)
Credential changes → Adam only (never agent-to-agent)
```
