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
