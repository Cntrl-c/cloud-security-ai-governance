# Rules of Engagement (ROE)

*Sample document. Fictional parties.*

No scanning or testing starts until this document is signed.

## 1. Authorization

The Client authorizes Provider to perform the testing below against the listed targets **only**, during approved windows. This document is the written permission testers carry during the engagement.

## 2. Targets

| Target | Subnet | Allowed |
|---|---|---|
| Domain controller | Business | Scan, enumerate, controlled exploitation |
| File server | Business | Scan, enumerate, controlled exploitation |
| Engineer workstation | Business | Scan, enumerate, controlled exploitation |
| Public web server | DMZ | Scan, web testing, controlled exploitation |
| VPN gateway | Public | Scan only; no exploitation (sole admin entry point) |

Anything not listed is **out of bounds**.

## 3. Allowed vs. Not Allowed

| ✅ Allowed | ❌ Not allowed |
|---|---|
| Port and service scanning | Production systems |
| Credentialed vulnerability scans | Denial-of-service or load testing (Phase 1) |
| Exploiting confirmed findings | Deleting or modifying Client data |
| Credential capture and relay *within scope* | Installing persistent backdoors |
| Lateral movement between in-scope hosts | Phishing or contacting employees |
| Screenshots and logs as evidence | Copying personal data off the environment |

## 4. Testing Windows

- Weekdays, 8:00 AM – 6:00 PM Pacific, unless the Client approves otherwise in writing
- Client takes snapshots of all in-scope hosts before each window

## 5. Origin

All testing comes from one approved assessment machine connected through the Client's VPN. Provider gives the Client its source address so activity can be told apart from a real attack.

## 6. Stop Conditions

Provider stops immediately and calls the Client contact if:
- A system becomes unstable or unreachable
- Evidence of a real attacker is found
- Personal or regulated data is unexpectedly exposed
- The Client asks to stop for any reason

## 7. Evidence Handling

- Stored encrypted, access limited to the test team
- Passwords captured during testing are reported (masked) and never reused outside scope
- Returned or destroyed 30 days after close, with written confirmation

## 8. Contacts

| Role | Name | Reachable |
|---|---|---|
| Client sponsor | [Client CISO] | Phone / email |
| Client technical contact | [IT Operations Lead] | During testing windows |
| Provider lead | [Engagement Lead] | Phone / email |

## Sign-off

| | Client | Provider |
|---|---|---|
| Name | [Client CISO] | [Engagement Lead] |
| Signature | ____________ | ____________ |
| Date | ____________ | ____________ |
