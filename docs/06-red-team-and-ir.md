# 06 – Red Team Evaluation & AI Incident Response

No live production AI environment was in scope, so the red team was **planned and simulated** against two further gates:

- **G6 – Control Resilience:** do controls hold under realistic AI attacks?
- **G7 – Incident Response Readiness:** can the organization detect, contain, and recover?

## Scenarios

| # | Scenario | OWASP LLM | Pass | Fail | Evidence |
|---|---|---|---|---|---|
| 1 | Direct prompt injection | Prompt Injection | Guardrails detect and block | Model behavior altered | Input/output guardrail and orchestrator logs |
| 2 | Indirect injection via RAG | Prompt Injection | Embedded instructions ignored | Retrieved text alters response | Vector DB queries, API Gateway logs |
| 3 | Sensitive info disclosure | Sensitive Info Disclosure | Nothing returned beyond user's access | Restricted data returned | AuthZ records, DLP logs |
| 4 | Excessive agent authority | Excessive Agency | Every privileged action needs HITL | Tool runs without approval | Execution gateway audit, approval records |
| 5 | Resource exhaustion | Unbounded Consumption | Service stays available under load | Service degraded or down | Gateway logs, resource metrics |

> OWASP category names follow the 2025 list; some earlier drafts used the 2023 numbering (e.g., LLM06, LLM08).

## AI Incident Response Playbook (Condensed)

1. **Detect** — guardrail alerts, HITL denials, DLP flags, anomalous rate-limit hits route to Security Operations.
2. **Triage** — review auth records, AI interaction logs, and guardrail logs to scope the event.
3. **Contain** — suspend the account; disable affected tools or data sources at the gateways if needed.
4. **Eradicate & recover** — purge poisoned documents, re-index, update guardrail rules, restore service.
5. **Notify** — leadership per comms plan; assess GDPR Art. 33 (72-hour regulator notice) and PDPO obligations if personal data is involved.
6. **Learn** — update playbook, guardrails, and gate criteria; brief executives.

## Tabletop Exercise: Repeated Prompt Injection

**Scenario:** an authenticated employee repeatedly tries to make the assistant ignore its instructions and reveal proprietary designs. The input guardrail fires and alerts Security Operations.

**Decisions made:** suspend the account pending review; escalate on repeated alerts; notify leadership; confirm no tool execution or disclosure occurred; tune detection rules.

**Gaps found:**

| Gap | Fix |
|---|---|
| No defined timeline for notifying executives | Set a notification SLA for confirmed incidents |
| No data classification policy, so "what was at risk" was unclear | Finalize the policy |
| On-call coverage undefined; response speed untested under real staffing | Run recurring tabletops with real staffing assumptions |
