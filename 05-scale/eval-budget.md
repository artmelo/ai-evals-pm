# Module 5 · Eval Budget · Ascend IQ

**Quarterly budget cap:** $200,000
**Online eval spend:** $180,000 (3 of at most 3 online evals)

## Budget

| Failure | Trust metric | Risk | Level | Cost |
| --- | --- | :---: | :---: | ---: |
| Data Fabrication | Hallucination Rate | P0 | Online eval | $85,000 |
| Context Specificity | Robustness | P1 | Online eval | $70,000 |
| Overconfident Tone | UX Trust | P1 | Periodic audit | $6,500 |
| Data Bias | Fairness | P2 | Periodic audit | $5,500 |
| Slow Answers | Latency | P3 | Online eval | $25,000 |

## Downgrades

### Periodic audit · Overconfident Tone (UX Trust · P1)
- **Cheaper check:** Every week, manually review 50 randomly sampled answers for unsupported claims, excessive confidence, and missing uncertainty statements. Flag misleading responses for correction.
- **Why it’s enough:** Weekly reviews catch recurring overconfidence patterns at 10% of online eval cost. Some issues may be missed between audits, but P0 factual errors remain covered by continuous online evaluation.

### Periodic audit · Data Bias (Fairness · P2)
- **Cheaper check:** Every two weeks, review 50 answers across US and APAC market questions, comparing factual accuracy, source representation, and regional relevance. Flag significant quality differences.
- **Why it’s enough:** Periodic regional comparisons detect systematic US bias at 10% of online eval cost. Some individual biased answers may be missed, but the P2 risk is acceptable with regular monitoring and escalation if disparities emerge.

