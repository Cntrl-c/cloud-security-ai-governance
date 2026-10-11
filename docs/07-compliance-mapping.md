# 07 – Compliance Mapping

Three offices, three legal regimes, plus enterprise and AI frameworks. One finding often triggers several obligations at once.

## Who Cares About What

| Framework | Applies to | Focus in this engagement |
|---|---|---|
| NIST SP 800-171 | US / San Diego | Access control, strong auth, encryption in transit, flaw remediation |
| ISO/IEC 27001:2022 | All regions | Annex A access control, identity, vulnerability mgmt, cryptography |
| GDPR | EU / Brussels | Art. 32 security of processing; Art. 33 breach notification |
| Hong Kong PDPO | Hong Kong | Data Protection Principle 4 (data security) |
| NIST AI RMF 1.0 | AI platform | Govern, Map, Measure, Manage |
| ISO/IEC 23894 | AI platform | AI risk identification and treatment |
| OWASP LLM Top 10 / MITRE ATLAS | AI platform | Threat catalog and adversary techniques |
| NIST SSDF | AI platform build | Secure development and component vetting |

## Phase 1 Findings → Obligations

| Control area | NIST 800-171 | ISO 27001 Annex A | GDPR Art. 32 | PDPO DPP4 | Findings |
|---|---|---|---|---|---|
| Patching | 3.14.1 | 8.8 | 32(1)(b) | Technical safeguards | VUL-001, 002, 004, 005, 007 |
| Access control / least privilege | 3.1.1, 3.1.2 | 5.15 | 32(1)(b) | Access controls | VUL-006, 008, 010, 014 |
| Authentication | 3.5.3 | 5.16 | 32(1)(b) | Access controls | VUL-013 |
| Encryption in transit | 3.13.8 | 8.24 | 32(1)(a) | Transmission | VUL-003, 009, 011, 012 |

## Open Gaps

| Gap | Impact | Owner | Status |
|---|---|---|---|
| **No data classification policy** | DLP, RAG scoping, GDPR/PDPO data mapping, and G2 can't be validated | Client leadership | **Open — launch blocker** |
| Cross-border data flows for AI | EU/HK personal data may be indexed and served to staff in other regions; transfer basis not documented | Client privacy / legal | Open |
| Executive incident notification SLA | GDPR's 72-hour window needs a faster internal clock | CISO | Open |
| Post-hardening validation scan | GDPR Art. 32(1)(d) "regularly testing" only partially met until rescan | Security team | Pending |

*This is a summary for portfolio purposes, not legal advice.*
