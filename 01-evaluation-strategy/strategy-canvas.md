# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).

## 1. Product Strategy, The Context

**Who it's for:** VP-level strategists and product leaders at Fortune 500 companies who pay upward of $50,000 a year for verified market intelligence.

**What they use it for:** Asking plain-language questions, like “Compare the pricing models of Stripe and Adyen,” and getting answers in seconds instead of digging through the platform.

**What's at stake:** Engagement is dropping, Q4 retention is at risk, and the CPO wants Ascend IQ live for the top 50 enterprise accounts next month. One poor answer to the wrong client can do lasting damage to the relationship.

## 2. Measurements, The Execution

**User promise.** For enterprise strategists and product leaders, Ascend IQ promises fast, accurate, and verifiable market intelligence answers, backed by trusted sources, so they can make high-stakes business decisions with confidence.

**Top 3 trust metrics:**
- **Latency**, Response speed (P95 / P99). Slow kills engagement.
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **Robustness**, Coherence on messy, adversarial, out-of-scope inputs.

**Why these three:** Hallucination Rate protects accuracy, 
Robustness protects reliability and appropriate handling of uncertainty;
Latency protects the promise of speed.

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Hallucination Rate ↔ Latency
We prioritize lower hallucination rates over latency because accurate, source-backed intelligence is more valuable than an instant but potentially misleading answer.

### Trade-off 2 · Latency ↔ Robustness
We prioritize robustness over latency because handling ambiguous and complex questions safely protects client trust, even if additional validation takes longer.

---
_Generated from the AI Evaluation Strategy Canvas, M1 lab tool, AI Evals Certification._
