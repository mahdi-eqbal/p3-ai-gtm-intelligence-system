# P3 Test Matrix

## System

AI-Assisted GTM Intelligence & Account Prioritization System

## Validated Scenarios

| Test | Expected Behavior | Result |
|---|---|---|
| Real company enrichment | Real domains are enriched with firmographic and company-context data | PASS |
| Synthetic record isolation | .example records are excluded from paid enrichment and signal monitoring | PASS |
| GTM job signal detection | Relevant GTM hiring signals are detected from real accounts | PASS |
| Multiple signal records | Multiple job postings for the same account are returned through multi-row lookup | PASS |
| Signal-to-account linkage | Job-posting signals are matched back to target accounts by domain | PASS |
| Signal context generation | Matched job records are converted into structured context for AI analysis | PASS |
| Signal-to-agent integration | Claygent consumes actual Clay signal context through dditionalContext | PASS |
| Web research fallback | Accounts without matched Clay job signals can still be researched through web sources | PASS |
| Evidence-aware AI | Facts, hypotheses, confidence, and uncertainty are separated | PASS |
| ICP classification | Accounts are classified using explicit ICP rules | PASS |
| Buyer persona selection | Persona is selected based on the strongest available GTM evidence | PASS |
| Raw response preservation | Original Claygent JSON response is retained | PASS |
| Structured output extraction | AI response fields are parsed into operational columns | PASS |
| Fit scoring | ICP classification is converted into deterministic numeric score | PASS |
| Signal scoring | Signal type is converted into deterministic signal score | PASS |
| Confidence scoring | AI confidence is converted into deterministic confidence score | PASS |
| Signal-date extraction | Latest matched job-posting date is extracted from Clay signal records | PASS |
| Timing scoring | Signal recency is converted into deterministic timing score | PASS |
| Priority scoring | Fit, signal, confidence, and timing scores are combined into a total score | PASS |
| Priority tiering | Accounts are classified into P1 / P2 / P3 / Review | PASS |
| Human-review governance | Evidence uncertainty can override automatic approval | PASS |
| Actionable delivery view | Auto-approved accounts are presented as prioritized GTM targets | PASS |
| Manual review queue | Uncertain real accounts are isolated for human review | PASS |
| Downstream CSV export | Actionable account data is successfully exported for downstream systems | PASS |

## Acceptance Cases

### High-Confidence Strong Signal

Attio and Hightouch reached P1 with high-confidence evidence and were routed to the Actionable Accounts view.

### Multiple Signals

Apollo returned multiple relevant Clay job-posting records and successfully linked them back to the same account.

### Evidence Uncertainty

Common Room received a valid P2 score but was routed to Manual Review because evidence uncertainty was detected.

### Signal Fallback

Usercentrics had no matched Clay job-posting signal but could still be analyzed through web research without inventing a Clay signal.

### Test-Data Isolation

Synthetic .example records were retained for logic testing but excluded from paid enrichment, signal monitoring, and operational delivery.

### Downstream Delivery

The Actionable Accounts view was successfully exported to CSV with GTM intelligence, scoring, priority, and recommended-action fields.

## Final System Path

Raw Account List
→ Real / Synthetic Separation
→ Company Enrichment
→ GTM Job Signal Monitoring
→ Signal-to-Account Multi-Row Lookup
→ Signal Context Generation
→ Claygent Web Research + Clay Signal Context
→ Structured GTM Intelligence
→ Deterministic Fit / Signal / Confidence Scoring
→ Signal Date Extraction
→ Timing / Recency Scoring
→ Total Priority Score
→ Priority Tier
→ Human Review Gate
→ Actionable Accounts / Manual Review Queue
→ CSV Delivery Export
