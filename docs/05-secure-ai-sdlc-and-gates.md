# 05 – Secure AI SDLC & Assurance Gates

The goal: make "is it safe to launch?" a decision backed by evidence, with a named owner, instead of a gut call.

## Lifecycle Checkpoints

| Phase | Decision Point | Owner |
|---|---|---|
| 1. Design & architecture review | Every threat has a mapped control at a named boundary before build starts | Security Architecture Board |
| 2. Model & tool onboarding | No new model, plugin, or agent tool connects until provenance is verified, scanned, and least-privileged | Engineering + Security Assessment |
| 3. Data ingestion & change mgmt | No new share is indexed until access scoping and integrity checks pass | Data Governance |
| 4. Pre-deployment evaluation | Go / no-go — all launch gates must pass | CISO |
| 5. Post-deployment monitoring | Weekly guardrail/HITL log review; monthly access and rate-limit review | Security Operations Lead |
| 6. Change control & re-evaluation | Any material change re-runs only the affected gates | Change Control Board |

This lines up with **NIST SSDF** (secure design, verify third-party components, respond to vulnerabilities) and the **NIST AI RMF** *Govern* function.

## Launch-Blocking Gates

| Gate | Confirms | Threats | Evidence | If it fails |
|---|---|---|---|---|
| **G1 – Guardrail Efficacy** | Guardrails block injection and unsafe output | 1, 2, 3, 5 | Red-team report, DLP tests, sanitization tests | Launch blocked; fix and re-run |
| **G2 – Data Governance** | RAG data is scoped, classified, integrity-checked | 3, 4 | Ingestion sign-off, hash/version audit trail, **finalized classification policy** | Launch blocked — **no exception** |
| **G3 – Agent Authority** | No tool runs without informed human approval | 6, 7 | Approval/denial logs, UI review | Launch blocked; fix HITL and re-test |
| **G4 – Platform Integrity** | Identity, availability, supply chain controls hold | 8, 9, 10 | IdP/WAF logs, load test, SBOM / hash checks | Launch blocked; escalates to CEO after one failed remediation cycle |

**Approval authority:** the client's CISO for all gates, with CEO escalation for unresolved G4 risk. Once approved, gate criteria are frozen for the release; changes go through formal change request, not informal edits.

## Why G2 Has No Exception

Several assurance activities (DLP validation, content-integrity checks) can only be tested against a definition of "restricted" or "personal data." Without a classification policy:

- DLP rules are built on guesses.
- GDPR (Brussels) and PDPO (Hong Kong) obligations can't be scoped.
- Gate evidence isn't defensible to an auditor.

**Recommendation to leadership:** finalize the data classification policy before scheduling the launch date.
