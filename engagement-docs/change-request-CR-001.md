# Change Request CR-001 — Security Hardening

*Sample document. Fictional parties.*

| | |
|---|---|
| **Project** | Secure Infrastructure Migration |
| **Requested by** | ABC Security |
| **Priority** | Must have |
| **Type** | Configuration · Patching · Risk mitigation |

## What's Changing

Add remediation work to the engagement. Apply patches, secure configuration baselines (CIS Benchmarks), protocol hardening, and authentication fixes across all five in-scope hosts.

## Why

Pen testing showed an attacker could **capture credentials, move laterally, and take over the domain**, mainly through missing patches, legacy authentication (NTLMv1), unsigned SMB, and unencrypted services. This blocks safe cutover and creates exposure under NIST SP 800-171, ISO/IEC 27001, GDPR, and PDPO.

## Impact

| Area | Impact |
|---|---|
| Scope | Adds remediation for VUL-001 to VUL-014 |
| Schedule | ~5 business days, in maintenance windows |
| Cost | Staff time only; no new hardware or licenses |
| Risk | Legacy apps may break when old protocols are disabled; tested in sandbox first |

## Options

| Option | Result |
|---|---|
| 1. Accept risk, do nothing | Proven domain-compromise path stays open |
| 2. Compensating controls only | Reduces exposure; root causes remain |
| **3. Full hardening (recommended)** | Removes root causes; largest risk reduction |

## Rollout & Rollback

1. Snapshot all hosts
2. Apply changes in sandbox and test business functions
3. Phased production rollout in maintenance windows
4. Rescan to confirm fixes

**Rollback:** restore snapshot, revert Group Policy, confirm services before closing.

## Done When

- No Critical or High findings remain
- The demonstrated attack path can't be reproduced
- Business services work normally

## Decision

☐ Approved ☐ Not approved ☐ Deferred

| | Client | Provider |
|---|---|---|
| Name | [Client CISO] | [Engagement Lead] |
| Signature | ____________ | ____________ |
| Date | ____________ | ____________ |
