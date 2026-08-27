# Implementation Summary

## AI-Assisted GTM Intelligence & Account Prioritization System

### Objective

Build an evidence-aware GTM intelligence workflow that transforms raw B2B target accounts into prioritized and operationally actionable GTM targets.

### Stack

- Clay
- Claygent
- Clay GTM Signals
- Company enrichment
- Web research
- Structured JSON
- Formula-based scoring and routing

### Operational Flow

Raw accounts
→ real/synthetic isolation
→ company enrichment
→ GTM job signal monitoring
→ multi-row signal lookup
→ signal context
→ Claygent web research
→ structured GTM intelligence
→ deterministic scoring
→ signal-date extraction
→ timing scoring
→ priority tier
→ human-review gate
→ actionable accounts / manual review
→ CSV delivery

### Key Architecture Decisions

#### Signal and research layers are connected

Clay job-posting signals are linked back to accounts by domain and passed into Claygent as structured context.

The AI layer therefore uses both observed Clay signals and independent web research.

#### AI does not control final priority

Claygent performs evidence-aware reasoning.

Final prioritization is deterministic and based on:

- ICP fit
- signal strength
- confidence
- timing

#### Raw AI output is preserved

The original JSON response remains available for audit while individual fields are parsed into operational columns.

#### Human review can override numerical priority

Accounts with material evidence uncertainty are routed to a Manual Review Queue even if their numerical score is otherwise high enough for action.

#### Test data is isolated

Synthetic .example records support logic testing but are excluded from paid enrichment, signal monitoring, and operational delivery.

### Validated Scenarios

The implementation validated:

- company enrichment
- signal monitoring
- multiple signals per account
- signal-to-account lookup
- signal-context generation
- Claygent web research
- evidence/inference separation
- ICP classification
- buyer-persona selection
- deterministic scoring
- signal recency scoring
- uncertainty-based human review
- actionable-account delivery
- CSV export

### Final Delivery

The system produces:

**Actionable Accounts**
for auto-approved, prioritized GTM targets.

**Manual Review Queue**
for accounts requiring human validation.

The actionable dataset was successfully exported to CSV for downstream use.

### What This Project Demonstrates

- Clay table architecture
- company enrichment
- GTM signal monitoring
- multi-table data resolution
- Claygent configuration
- evidence-backed AI research
- AI guardrails
- structured-output handling
- deterministic account scoring
- recency logic
- human-in-the-loop governance
- operational GTM delivery

### Project Positioning

This is an independently designed and built professional GTM Engineering / Revenue Systems case study.

No client, employer, production deployment, commercial result, or paid engagement is claimed.
