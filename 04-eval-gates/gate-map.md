# Module 4 · Eval Gate Map · Ascend IQ Copilot

## Gate Map

| Row | Failure Mode | Severity | Placement | Rationale |
|---|---|---|---|---|
| 1 | Hallucination | Hard | Release | Incorrect enterprise pricing can mislead high-value business decisions and put $50K+ client relationships at risk; this P0 failure must block release. |
| 14 | Relevance | No gate |  | The refusal follows the stated safety policy, so the relevance failure is a false alarm and should not block release. |
| 17 | Tone | Advisory | Pull Request | Unprofessional language weakens brand credibility, but the impact is recoverable and does not justify blocking a release. |
| 5 | Hallucination | Soft | Staging | Presenting an invited speaker as confirmed damages intelligence credibility and requires correction or documented approval before release. |
| 8 | Hallucination | Soft | Staging | Misrepresenting competitor API limits can distort strategic decisions, requiring correction or documented risk acceptance before release. |
| 3 | Latency | Advisory | Staging | The accurate answer took 4.2 seconds against a 2.0-second target, hurting engagement but not creating enough risk to block release. |

## After the pushback

I kept the gates but strengthened enforcement: Row 1 requires source freshness checks, Row 8 requires Product-approved overrides, and Row 14 remains No gate due to a false positive. The rest balance risk and release speed.

## Sample Interactions

**Row 1**
- Input: What is InsightFlow's pricing for Enterprise?
- Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- What's true: Pricing page: the price changed from $49 to $59 a month yesterday.
- Automated eval: Fail · Hallucination. The answer quotes the old price as current.
- My call: Hard at Release. Incorrect enterprise pricing can mislead high-value business decisions and put $50K+ client relationships at risk; this P0 failure must block release.

**Row 14**
- Input: Summarize the lawsuit mentioned in the WSJ about Competitor Z.
- Output: I cannot provide summaries of ongoing legal litigation.
- What's true: Safety guidelines: “Refuse legal queries.”
- Automated eval: Fail · Relevance. The answer doesn’t answer the question.
- My call: No gate. The refusal follows the stated safety policy, so the relevance failure is a false alarm and should not block release.

**Row 17**
- Input: Draft a cold email about our new feature.
- Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
- What's true: Brand voice: confident, professional, expert. Avoid slang.
- Automated eval: Fail · Tone. Slang detected.
- My call: Advisory at Pull Request. Unprofessional language weakens brand credibility, but the impact is recoverable and does not justify blocking a release.

**Row 5**
- Input: List the confirmed speakers for SaaStr.
- Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- What's true: Agenda: Lemkin and Levie are confirmed. Sam Altman is invited, not confirmed.
- Automated eval: Fail · Hallucination. Lists an unconfirmed speaker as confirmed.
- My call: Soft at Staging. Presenting an invited speaker as confirmed damages intelligence credibility and requires correction or documented approval before release.

**Row 8**
- Input: Compare our API rate limits to Competitor Z.
- Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
- What's true: Tech specs: our API allows 500 requests a minute, and Competitor Z allows 1,000.
- Automated eval: Fail · Hallucination. Contradicts the specs and criticizes a named competitor.
- My call: Soft at Staging. Misrepresenting competitor API limits can distort strategic decisions, requiring correction or documented risk acceptance before release.

**Row 3**
- Input: Summarize the top 3 complaints from DataViz's G2 reviews.
- Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
- What's true: G2 reviews: the three complaints are correct. The answer took 4.2 seconds, and the target is 2.0.
- Automated eval: Fail · Latency. Exceeded the maximum response time.
- My call: Advisory at Staging. The accurate answer took 4.2 seconds against a 2.0-second target, hurting engagement but not creating enough risk to block release.
