# 04 – Threat Model & Control Catalog

Ten threats were enumerated directly from the target-state architecture: seven AI-specific and three infrastructure threats that the AI platform inherits.

## Threats, Controls, and Residual Risk

| # | Threat | Type | Primary Control | Boundary | Residual Risk |
|---|---|---|---|---|---|
| 1 | Direct prompt injection | AI | Input Guardrail | Inference | Partially mitigated — accepted (HITL contains impact) |
| 2 | Indirect prompt injection via RAG documents | AI | API Gateway (user-context retrieval) | Authorization | Partially mitigated — accepted (known RAG limitation) |
| 3 | Sensitive information disclosure | AI | API Gateway + Output Guardrail (DLP) | Authorization + Inference | Mitigated |
| 4 | RAG data poisoning | AI | API Gateway (write-access scoping) | Authorization | Partially mitigated — accepted (relies on AD hygiene) |
| 5 | Improper output handling (XSS, scripts) | AI | Output Guardrail | Inference | Mitigated |
| 6 | Excessive agent authority | AI | Tool Execution Gateway (HITL) | Execution | Mitigated |
| 7 | Human approval manipulation | AI | HITL shows raw command, not just AI summary | Execution | Partially mitigated — accepted (training for click fatigue) |
| 8 | Identity token misuse / replay | Infra | SSO/MFA + WAF | Edge | Mitigated |
| 9 | Resource exhaustion (DoS) | Infra | WAF rate limits + prompt size limits | Edge + Inference | Partially mitigated — accepted |
| 10 | AI supply chain compromise | Infra | Default-deny egress on LLM host | Infrastructure | Partially mitigated — sandboxing deferred |

## Control Catalog

| Control | Type | Threats | Evidence |
|---|---|---|---|
| Cloud WAF | Preventive | 8, 9 | Traffic and block logs |
| SSO / MFA | Preventive | 8 | IdP authentication logs |
| API Gateway / Identity Broker | Preventive | 2, 3, 4 | Access and token validation logs |
| Input Guardrail | Preventive / Detective | 1, 9 | Dropped-prompt logs, signature alerts |
| Output Guardrail | Preventive / Detective | 3, 5 | DLP flags, redaction logs |
| Tool Execution Gateway (HITL) | Preventive | 6, 7 | Timestamped approval and execution logs |
| Host-based ACLs (egress deny) | Preventive | 10 | Firewall drop logs |

## Known Limits (Being Honest With the Client)

- **Guardrails aren't perfect.** Novel semantic injections can slip past signature/heuristic filters. Defense-in-depth (HITL, isolation) limits the damage.
- **Poisoned text inside a legitimate file is hard to detect.** User-scoped retrieval shrinks the blast radius; it doesn't remove the payload.
- **Humans get tired.** Showing the raw command helps, but approval fatigue is a people problem, handled with training and review.
- **DLP needs definitions.** Without a data classification policy, "sensitive" is ad hoc, which weakens threats 3 and 4.

## Framework Alignment

- **OWASP LLM Top 10:** prompt injection, sensitive information disclosure, data/model poisoning, improper output handling, excessive agency, unbounded consumption, supply chain.
- **MITRE ATLAS:** used to describe adversary techniques for injection, poisoning, and exfiltration during red-team planning.
- **NIST AI RMF / ISO/IEC 23894:** threats and residual-risk decisions map to the *Map* and *Manage* functions and the ISO risk treatment process.
