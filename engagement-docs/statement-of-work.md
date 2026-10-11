# Statement of Work (SOW)

*Sample document. Fictional parties. Not a real contract.*

| | |
|---|---|
| **Client** | XYZ Design Co. ("Client") |
| **Provider** | ABC Security ("Provider") |
| **Engagement** | Secure Infrastructure Migration — Phase 1 |
| **SOW No.** | XYZ-ABC-001 |

## 1. Purpose

Provider will assess and test the Client's private cloud environment before production cutover, and recommend fixes that reduce risk and support the Client's compliance obligations.

## 2. Scope

**In scope**
- Five hosts in the Client's isolated test environment: domain controller, file server, engineer workstation, public web server, VPN gateway
- Business, DMZ, and public subnets
- Configuration and patch review, vulnerability scanning, controlled penetration testing

**Out of scope**
- Live production systems
- Employee personal devices
- The cloud provider's management platform
- Social engineering and physical testing
- Fixing issues (Client performs remediation unless added by change request)

## 3. Deliverables

| # | Deliverable | Description |
|---|---|---|
| D1 | System & Security Requirements | What "secure" means for this environment, mapped to compliance |
| D2 | Vulnerability Assessment Plan | Method, tools, schedule, risk scoring |
| D3 | Vulnerability Assessment Report | Prioritized findings with fixes |
| D4 | Penetration Test Plan | Attack scenarios, limits, evidence handling |
| D5 | Penetration Test Report | What was exploitable and why it matters |
| D6 | Hardening Recommendations | Prioritized remediation roadmap |

## 4. Approach

- Risk scoring with **CVSS v3.1**
- Testing aligned to **NIST SP 800-115**
- Findings mapped to NIST SP 800-171, ISO/IEC 27001:2022, GDPR, and Hong Kong PDPO
- All testing governed by the signed [Rules of Engagement](rules-of-engagement.md)

## 5. Timeline (Indicative)

| Week | Activity |
|---|---|
| 1 | Kickoff, requirements (D1) |
| 2 | Assessment plan (D2), scanning |
| 3 | Assessment report (D3), pen test plan (D4) |
| 4 | Pen testing, report (D5) |
| 5 | Hardening recommendations (D6), executive readout |

## 6. Client Responsibilities

- Provide network diagram, asset list, and test credentials
- Name a technical point of contact available during testing windows
- Fix or formally accept all **Critical** findings before pen testing begins
- Approve deliverables within 5 business days

## 7. Acceptance

A deliverable is accepted when the Client sponsor signs off or raises no written objection within 5 business days. One round of revisions per deliverable is included.

## 8. Changes

Any change to scope, timeline, or cost requires a written change request signed by both parties. (See CR-001 and CR-002.)

## 9. Confidentiality & Data Handling

- Findings and evidence are confidential and shared only with named Client contacts.
- Evidence is stored encrypted and deleted or returned 30 days after engagement close.
- Any personal data encountered is not copied, and is reported to the Client only by location and type.

## Sign-off

| | Client | Provider |
|---|---|---|
| Name | [Client CISO] | [Engagement Lead] |
| Signature | ____________ | ____________ |
| Date | ____________ | ____________ |
