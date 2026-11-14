You are helping a PM turn an eval spec into short messages for three teams. Use plain, direct language and keep every number from the spec exactly as it is.

MY SPEC
Target risk: Wrong Pricing (#HALLUCINATION), an output risk
Evaluator: The rule check from Lab 1
Threshold: 100% of known outdated pricing cases must be caught by the rule check, with zero false alarms on verified correct pricing. Any missed P0 pricing hallucination blocks release.
What supports the threshold: the rule check caught 1 of 1, the safety rule caught 1 of 1, the judge caught 1 of 1The rule check caught 1/1 P0 failures with 0 misses and 0 false alarms; the safety rule and judge also caught 1/1. This supports the approach, but additional test cases are needed to validate the threshold.
Business stakes: Outdated pricing presented as verified intelligence can mislead enterprise decisions, damage client trust, and put $50K+ annual subscriptions at risk, especially during rollout to the top 50 accounts.
Owner: Engineering owns automated validation and release enforcement; AI Quality owns evaluation coverage and ongoing monitoring; Product owns risk acceptance and the final ship-or-hold recommendation.

Write three messages, one or two sentences each:
- Engineering: the acceptance criteria, as an exact pass and fail rule, so an engineer could build the check without asking a question.
- Design: what the user sees when the check blocks an answer.
- Leadership: the risk this removes, and why it is worth the cost.

Reply with the complete contents of a file called eval-spec.md, in exactly this format and nothing else:

# Eval Spec · Wrong Pricing (#HALLUCINATION), an output risk

| Part | Spec |
|---|---|
| Target risk | [from my spec] |
| Evaluator | [from my spec] |
| Threshold | [from my spec, with what supports it] |
| Business stakes | [from my spec] |
| Owner | [from my spec] |

## Messages

**Engineering · acceptance criteria:** Compare every quoted price and billing unit against the latest verified pricing reference. PASS (1) only when they match and all pricing terms are supported; FAIL (0) on any mismatch, outdated price, or unsupported condition, blocking the response and release if a P0 case is missed.

**Design · what the user sees:** When pricing cannot be verified, show: "We couldn't verify the latest pricing. Please check the official pricing source." Never display outdated pricing as confirmed or silently substitute an estimate.

**Leadership · risk and return:** This check reduces the risk of incorrect pricing intelligence damaging enterprise decisions and jeopardizing $50K+ annual subscriptions across the top 50 accounts. A deterministic rule provides fast, low-cost protection, but the initial 1/1 result must be validated against a broader test set before launch.
