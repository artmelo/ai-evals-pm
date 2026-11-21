# Eval Spec · Wrong Pricing (#HALLUCINATION), an output risk

| Part | Spec |
|---|---|
| Target risk | Wrong Pricing (#HALLUCINATION), an output risk |
| Evaluator | The rule check from Lab 1 |
| Threshold | 100% of known outdated pricing cases must be caught, with zero false alarms on verified correct pricing. Any missed P0 pricing hallucination blocks release. |
| Business stakes | Outdated pricing can mislead enterprise decisions, damage client trust, and put $50K+ annual subscriptions at risk during rollout to the top 50 accounts. |
| Owner | Engineering owns validation and release enforcement; AI Quality owns evaluation coverage and monitoring; Product owns risk acceptance and the final ship-or-hold recommendation. |

**Threshold evidence:** The rule check caught 1/1 P0 failures with 0 misses and 0 false alarms; the safety rule and judge also caught 1/1. Additional test cases are required to validate the threshold.

## Messages

**Engineering · acceptance criteria:** Compare every quoted price and billing unit against the latest verified pricing reference. PASS (1) only when they match and all pricing terms are supported; FAIL (0) on any mismatch, outdated price, or unsupported condition, blocking the response and release if a P0 case is missed.

**Design · what the user sees:** When pricing cannot be verified, show: "We couldn't verify the latest pricing. Please check the official pricing source." Never display outdated pricing as confirmed or silently substitute an estimate.

**Leadership · risk and return:** This check reduces the risk of incorrect pricing intelligence damaging enterprise decisions and jeopardizing $50K+ annual subscriptions across the top 50 accounts. A deterministic rule provides fast, low-cost protection, but the initial 1/1 result must be validated against a broader test set before launch.
