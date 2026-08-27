# P3 — AI-Assisted GTM Intelligence & Account Prioritization System

## Overview

An end-to-end GTM intelligence implementation that transforms raw B2B account data into evidence-backed, prioritized and operationally actionable target accounts.

The system combines Clay company enrichment, live GTM job signals, Claygent web research, structured AI reasoning, deterministic scoring, human-review governance, and delivery-ready outputs.

## Business Problem

Revenue teams often have target-account lists but lack a reliable way to determine:

- which accounts actually fit the ICP
- which accounts show meaningful recent GTM activity
- why an account may be relevant now
- what GTM or revenue problem may exist
- which buyer persona is most relevant
- which accounts should be prioritized
- when AI-generated research requires human review

This implementation turns those questions into a repeatable GTM intelligence workflow.

## Final System Architecture

Raw Account List
→ Real / Synthetic Record Separation
→ Company Enrichment
→ GTM Job Signal Monitoring
→ Signal-to-Account Multi-Row Lookup
→ Signal Context Generation
→ Claygent Web Research + Clay Signal Context
→ Structured GTM Intelligence
→ Deterministic Scoring
→ Timing / Recency Scoring
→ Priority Tier
→ Human Review Gate
→ Actionable Accounts / Manual Review Queue
→ CSV Delivery Export

## Core Capabilities

### Account Enrichment

Real company domains are enriched in Clay with firmographic and company-context data.

Synthetic .example records are retained for logic testing but excluded from paid enrichment and production-like signal monitoring.

### GTM Signal Monitoring

Clay Job Posting Signals identify relevant GTM hiring activity across target accounts.

### Signal-to-Account Resolution

A multi-row lookup links job-posting events back to target accounts using company domain.

This supports zero, one, or multiple signals per account.

### Signal Context

Matched signal records are summarized into account-level context and passed directly into the AI research layer.

### Claygent GTM Intelligence

A custom Claygent produces:

- ICP fit
- ICP fit reasoning
- recent GTM signal
- signal evidence
- why-now analysis
- likely GTM problem
- primary buyer persona
- confidence level
- uncertainty notes

The agent uses both web research and Clay signal context.

### AI Guardrails

The agent is instructed to:

- distinguish facts from inference
- avoid fabricating company facts
- avoid inventing buying intent
- frame GTM problems as hypotheses
- expose uncertainty
- report confidence

### Structured Output

The original Claygent JSON response is preserved while individual fields are extracted into operational columns.

### Deterministic Prioritization

Final account priority is not decided directly by AI.

Structured outputs are converted into:

- ICP Fit Score
- Signal Score
- Confidence Score
- Timing Score
- Total Priority Score

Priority tiers:

- P1
- P2
- P3
- Review

### Signal Timing

The latest matched job-posting date is extracted and converted into recency score:

- within 30 days → 10
- 31–90 days → 7
- 91–180 days → 3
- older / unavailable → 0

### Human-in-the-Loop Governance

A separate review layer evaluates confidence, evidence uncertainty, and priority state.

Accounts with material uncertainty are routed to Manual Review even when their numeric score would otherwise qualify them for action.

### Delivery Layer

The system produces:

- Actionable Accounts
- Manual Review Queue

The Actionable Accounts dataset was successfully exported to CSV for downstream use.

## Validation

Validated behaviors include:

- real company enrichment
- synthetic-record isolation
- GTM job signal detection
- multiple signal records
- signal-to-account lookup
- signal context generation
- Clay signal context passed into Claygent
- web research fallback
- evidence/inference separation
- ICP classification
- buyer-persona selection
- raw JSON preservation
- structured output extraction
- deterministic fit, signal, confidence, and timing scoring
- signal-date extraction
- priority tiering
- uncertainty-based human review
- actionable delivery view
- manual-review queue
- downstream CSV export

See TEST-MATRIX.md for the complete validation matrix.

## Tools

- Clay
- Claygent
- Clay Signals
- Clay company enrichment
- Web research
- Formula logic
- Structured JSON
- CSV delivery

## Project Positioning

This is an independently designed and built professional GTM Engineering / Revenue Systems implementation case study.

It does not represent a client deployment, employer implementation, production revenue result, or paid engagement.
