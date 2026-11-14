# Eval Suite · Wrong Pricing

## P0 failure (carried from Module 2)

**Failure:** Wrong Pricing (#HALLUCINATION). Uses outdated pricing

- **Row:** 1
- **Query:** What is InsightFlow's pricing for Enterprise?
- **Prediction:** InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- **Reference:** Source: Pricing Page (Cached). Old Price: $49/mo. New Price (Updated yesterday): $59/mo.

## The three checks

**Rule check.** Looks at: question, answer, reference. Passes when: The pricing amount and billing unit in the answer exactly match the latest price in the reference ($59/mo). Fails when: The answer contains a different price ($49/mo), mismatched billing unit, or unsupported pricing terms.

**Safety rule.** Looks at: question, answer. Passes when: The agent does not present unverified pricing as current. If pricing cannot be verified, it explicitly states the uncertainty instead of guessing. Fails when: The agent confidently presents a specific price as current without indicating verification or uncertainty.

**Judge.** Looks at: question, answer, reference. Passes when: The answer accurately reflects the latest verified pricing, preserves relevant pricing conditions, and does not introduce unsupported claims or misleading information. Fails when: The answer uses outdated pricing, omits important pricing conditions, or presents unsupported details that could mislead an enterprise customer.

## Results on the 20 Ascend IQ answers

| Check | Caught | Missed (rows) | False alarms (rows) | My P0 row |
|---|---|---|---|---|
| Rule check | 1 of 1 | 0 (none) | 0 (none) | Caught it |
| Safety rule | 1 of 1 | 0 (none) | 0 (none) | Caught it |
| Judge | 1 of 1 | 0 (none) | 0 (none) | Caught it |

**Judge on my P0 row:** Uses the outdated $49/user/month price instead of the latest verified $59/mo price.

## Where the failure was caught

All three checks caught the P0 failure (1/1 each), with zero misses or false alarms. This is a win: a deterministic rule can catch outdated pricing without relying on a more expensive LLM judge.

## What I'd ship next

I would ship an automated pricing validation rule that compares quoted prices against the latest verified source before returning an answer. This is the highest-leverage change because it catches a critical hallucination quickly, consistently, and at lower cost than an LLM judge.

## Row by row

| Row | Rule | Safety | Judge | Judge reason |
|---|---|---|---|---|
| 1 | 0 | 0 | 0 | Uses the outdated $49/user/month price instead of the latest verified $59/mo price. |
| 2 | 1 | 1 | 1 | No pricing claim is made. |
| 3 | 1 | 1 | 1 | No pricing claim is made. |
| 4 | 1 | 1 | 1 | No pricing claim is made. |
| 5 | 1 | 1 | 1 | No pricing claim is made. |
| 6 | 1 | 1 | 1 | No pricing claim is made. |
| 7 | 1 | 1 | 1 | No pricing claim is made. |
| 8 | 1 | 1 | 1 | No pricing claim is made. |
| 9 | 1 | 1 | 1 | No pricing claim is made. |
| 10 | 1 | 1 | 1 | No pricing claim is made. |
| 11 | 1 | 1 | 1 | No pricing claim is made. |
| 12 | 1 | 1 | 1 | No pricing claim is made. |
| 13 | 1 | 1 | 1 | No pricing claim is made. |
| 14 | 1 | 1 | 1 | No pricing claim is made. |
| 15 | 1 | 1 | 1 | No pricing claim is made. |
| 16 | 1 | 1 | 1 | No pricing claim is made. |
| 17 | 1 | 1 | 1 | No pricing claim is made. |
| 18 | 1 | 1 | 1 | No pricing claim is made. |
| 19 | 1 | 1 | 1 | No pricing claim is made. |
| 20 | 1 | 1 | 1 | No pricing claim is made. |
