# Change Request CR-002 — Enterprise AI Platform Expansion

*Sample document. Fictional parties.*

| | |
|---|---|
| **Project** | Secure Infrastructure Migration → Phase 2 |
| **Requested by** | XYZ Design Co. (Client CISO) |
| **Priority** | Must have before AI launch |
| **Type** | Scope expansion · Architecture · Governance |

## What's Changing

Expand the engagement from infrastructure testing to **security architecture, governance, and launch readiness** for the Client's planned internal AI assistant (local LLM, document search/RAG, and agent tools for shell, file, and email).

**Phase 1 work stays in place.** Phase 2 builds on its findings and hardening.

## Why

The AI assistant will read sensitive project files and can take real actions. Leadership needs an independent view of the risks, the controls required, and clear criteria for deciding whether it's safe to launch.

## Added Deliverables

| # | Deliverable |
|---|---|
| D7 | AI Case Review & Security Requirements |
| D8 | Current-State Architecture Review |
| D9 | Secure Target-State Architecture |
| D10 | Threat Model & Control Catalog |
| D11 | Secure AI SDLC & Launch Gates (G1–G5) |
| D12 | Red-Team Evaluation & AI Incident Response Package (G6–G7) |
| D13 | Executive risk briefing and go/no-go recommendation |

## Added Frameworks

NIST AI RMF 1.0 · ISO/IEC 23894 · OWASP Top 10 for LLM Applications · MITRE ATLAS · NIST SSDF (SP 800-218)

## Scope Limits

- AI platform stays on the private cloud; no external AI services
- Red-team activity is **planned and simulated**, not run against production
- Model training or fine-tuning is out of scope

## Impact

| Area | Impact |
|---|---|
| Schedule | Adds roughly one academic term of work |
| Cost | Additional consulting time per the master agreement |
| Dependencies | **Client must finalize a data classification policy** — required to pass launch gate G2 |

## Decision

☐ Approved ☐ Not approved ☐ Deferred

| | Client | Provider |
|---|---|---|
| Name | [Client CISO] | [Engagement Lead] |
| Signature | ____________ | ____________ |
| Date | ____________ | ____________ |
