# Secure Infrastructure & Enterprise AI Security Engagement

A two-phase, simulated consulting engagement completed as a graduate cybersecurity engineering capstone. Acting as a security firm (**ABC Security**), our three-person team assessed the private cloud of an international design company (**XYZ Design Co.**), then designed the security architecture, governance, and launch criteria for its planned in-house AI assistant.

> **Note:** The client, firm, people, and environment are fictional. All testing ran in an isolated lab sandbox. Hostnames, IPs, names, and raw scan output have been removed or generalized. The contract documents in [`engagement-docs/`](engagement-docs) are **our own original samples** written to role-play the full engagement; the instructor-provided originals are not included.

---

## At a Glance

| | Phase 1: Infrastructure | Phase 2: Enterprise AI Platform |
|---|---|---|
| **Goal** | Find and fix weaknesses before cloud cutover | Make a local LLM + RAG assistant safe to launch |
| **Work** | Requirements → Vuln Assessment → Pen Test → Hardening Plan | Architecture Review → Threat Model → Secure AI SDLC → Red Team & IR |
| **Key result** | 950 confirmed findings across 5 hosts; credential capture → domain compromise path shown; hardening plan approved | Target-state architecture with 4 trust boundaries, 10 threats mapped to controls, 4 launch-blocking gates |
| **Frameworks** | NIST SP 800-171, NIST SP 800-115, CVSS v3.1, CIS Benchmarks | NIST AI RMF, ISO/IEC 23894, OWASP LLM Top 10, MITRE ATLAS, NIST SSDF |

**Compliance scope (both phases):** NIST SP 800-171 · ISO/IEC 27001:2022 · GDPR (EU office) · Hong Kong PDPO (HK office)

---

## My Role

Three-person team; I contributed across both phases, with my main focus on:

- Running the Nmap and Nessus vulnerability scans in Phase 1
- Designing the launch-blocking security gates for the AI platform in Phase 2
- Contributing to the hardening plan, AI threat model, and incident response playbook

---

## Repository Layout

| File | What's inside |
|---|---|
| [Engagement Docs (sample)](engagement-docs) | Our own Client Brief, SOW, SLA, Rules of Engagement, and two Change Requests |
| [01 – Engagement Overview](docs/01-engagement-overview.md) | Client, scope, rules of engagement, how Phase 2 builds on Phase 1 |
| [02 – Infrastructure Assessment](docs/02-infrastructure-assessment.md) | Vulnerability assessment, pen test approach, hardening plan |
| [03 – AI Security Architecture](docs/03-ai-architecture.md) | Current-state problems, target-state design, trust boundaries |
| [04 – Threat Model & Controls](docs/04-threat-model-and-controls.md) | 10 threats, control catalog, residual risk |
| [05 – Secure AI SDLC & Gates](docs/05-secure-ai-sdlc-and-gates.md) | Lifecycle checkpoints and launch-blocking assurance gates |
| [06 – Red Team & Incident Response](docs/06-red-team-and-ir.md) | Simulated AI attack scenarios, IR playbook, tabletop lessons |
| [07 – Compliance Mapping](docs/07-compliance-mapping.md) | Cross-border obligations and open gaps |
| [References](docs/references.md) | APA 7th edition |

---

## Key Takeaways

1. **Patch hygiene was the biggest infrastructure risk.** Most critical findings were missing OS and library updates, not exotic flaws.
2. **Legacy protocols turn small issues into domain compromise.** NTLMv1, unsigned SMB, Telnet, and FTP made lateral movement easy.
3. **Treat the LLM as untrusted.** The safest design isolates the model from the network and from tools, and puts guardrails on both sides.
4. **One shared service account breaks AI access control.** RAG must retrieve data *as the user*, not as a super-user.
5. **Humans approve state changes.** Shell, file-write, and email actions require approval that shows the *raw* command, not just the AI's summary.
6. **Governance gaps block launch.** No finalized data classification policy means DLP and GDPR/PDPO scoping can't be fully validated, so it's a hard launch blocker.

---

## Team Tools & Methods

- Vulnerability assessment and CVSS-based prioritization (Nmap, Nessus, Nikto)
- Penetration test planning (NIST SP 800-115; Impacket, CrackMapExec, Metasploit, Wireshark)
- Change management (change request, rollback plan, validation criteria)
- Secure architecture and trust-boundary design for LLM/RAG/agent systems
- AI threat modeling (OWASP LLM Top 10, MITRE ATLAS)
- Assurance gate design, evidence models, and incident response planning
- Multi-jurisdiction compliance mapping (US, EU, Hong Kong)

---

## Author

**Cole Winship** — [github.com/Cntrl-c](https://github.com/Cntrl-c)

The underlying engagement was completed by a three-person graduate capstone team. This repository — the write-up, structure, and presentation of the work — is my own, built as a portfolio piece. It is a rewritten summary, not the original graded submission.
