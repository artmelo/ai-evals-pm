# Module 4 · Launch Strategy · Ascend IQ Copilot

## 4.0 Release Criteria

| Gate | Failure | Metric | Threshold | Dataset | Method | Runs at |
|---|---|---|---|---|---|---|
| Hard | Wrong Pricing (#HALLUCINATION) | % of pricing answers matching the latest verified pricing reference | 100% of known outdated pricing cases must be caught by the rule check, with zero false alarms on verified correct pricing. Any missed P0 pricing hallucination blocks release. | Ascend IQ golden set | Code-based check | Release |
| Soft | Row 8 · Hallucination: contradicts the specs and criticizes a named competitor | % of competitive API comparisons containing materially incorrect or unsupported claims. | 0% unreviewed material inaccuracies; 100% corrected or approved with documented overrides. | Ascend IQ golden set | LLM judge | Staging |
| Advisory | Row 3 · Latency: exceeded the maximum response time | Response time in seconds | ≤ 2.0 seconds per evaluated response | Ascend IQ golden set | Code-based check | Staging |

## CI Gate Request for Engineering

- **Hard gate · Wrong Pricing (#HALLUCINATION).** Check: the code-based check, run on the Ascend IQ golden set at Release. Measures: % of pricing answers matching the latest verified pricing reference. Passes when: 100% of known outdated pricing cases must be caught by the rule check, with zero false alarms on verified correct pricing. Any missed P0 pricing hallucination blocks release. On a fail: block the release.
- **Soft gate · Row 8 · Hallucination: contradicts the specs and criticizes a named competitor.** Check: the LLM judge, run on the Ascend IQ golden set at Staging. Measures: % of competitive API comparisons containing materially incorrect or unsupported claims.. Passes when: 0% unreviewed material inaccuracies; 100% corrected or approved with documented overrides.. On a fail: pause the release until the PM signs off on an override.
- **Advisory gate · Row 3 · Latency: exceeded the maximum response time.** Check: the code-based check, run on the Ascend IQ golden set at Staging. Measures: Response time in seconds. Passes when: ≤ 2.0 seconds per evaluated response. On a fail: post a warning, and don't block.

## Mitigation Plan · Soft Gate

If our Soft Gate fails due to inaccurate competitor API comparisons, I recommend a staged rollout to 5% of users, with documented Product approval. This limits exposure while we collect data, correct inaccuracies, and roll back if the failure rate exceeds our threshold.
