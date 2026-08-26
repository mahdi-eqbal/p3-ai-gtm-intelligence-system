# Evidence and AI Guardrails

## Core Rule

AI must not convert an unsupported inference into a verified fact.

## Claim Classes

### Confirmed Fact

Directly supported by a reliable source.

Examples:

- company announced funding
- official careers page lists RevOps roles
- company website states employee / product information

### Inference

Reasonable interpretation based on available evidence.

Example:

Hiring multiple GTM Operations roles may indicate growing operational complexity.

The system must label this as an inference.

### Uncertain

Insufficient or conflicting evidence.

The system must preserve uncertainty rather than force a conclusion.

## Evidence Quality

### High

Examples:

- official company website
- official careers page
- regulatory filing
- company press release
- verified executive statement

### Medium

Examples:

- reputable business publication
- established company database
- credible industry source

### Low

Examples:

- weak aggregator
- unsourced directory
- ambiguous social claim

## AI Output Rules

AI must:

1. reference available evidence
2. distinguish facts from hypotheses
3. state confidence
4. expose uncertainty
5. avoid inventing company facts
6. avoid inventing technologies in use
7. avoid inventing buying intent
8. avoid fabricating pain points as confirmed facts

## Human Review Triggers

Send to review when:

- evidence is conflicting
- evidence quality is low
- key account identity is uncertain
- signal date cannot be verified
- AI confidence is low
- a high-priority recommendation depends mainly on inference

## Portfolio Principle

The project should demonstrate controlled AI reasoning, not unrestricted AI content generation.
