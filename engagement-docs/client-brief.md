# Client Brief — XYZ Design Co.

*Sample document. Fictional client.*

## Who They Are

XYZ Design Co. is an architecture and engineering design firm of about 300 staff. Offices are in **San Diego** (HQ), **Hong Kong**, and **Brussels**. Clients are international, and many projects involve confidential building designs and client personal data.

## What's Happening

1. **Private cloud move.** XYZ Design Co. is moving core systems (Active Directory, file storage, public website, engineer workstations, remote access VPN) into a private cloud. Leadership wants proof it's secure before cutover.
2. **AI assistant.** Engineers want an internal assistant that can search past project files, answer questions, and automate small tasks (write reports, send emails, run scripts). Leadership likes the productivity gain but is worried about leaks and liability.

## What They Asked For

- An independent check of the new environment: find weaknesses, prove which ones matter, and recommend fixes.
- Later: help deciding whether the AI assistant is safe to launch and what guardrails it needs.

## Their Constraints

- Everything stays on their private cloud. **No public AI services** (no sending files to external chatbots).
- Must satisfy US, EU, and Hong Kong obligations at the same time.
- Limited budget; prefers fixing configuration over buying new tools.

## Known Weak Spots (Client Self-Reported)

- Patching has been "whenever someone has time."
- Some old protocols were left on for legacy apps.
- **No formal data classification policy.** Staff "just know" what's sensitive.

## Compliance Drivers

| Driver | Why |
|---|---|
| NIST SP 800-171 | US contracts with controlled data |
| ISO/IEC 27001:2022 | Certification target across all offices |
| GDPR | Brussels office and EU clients |
| Hong Kong PDPO | Hong Kong office and clients |
