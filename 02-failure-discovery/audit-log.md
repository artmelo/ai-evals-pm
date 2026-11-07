# Ascend IQ Failure Audit

8 confirmed failures: #HALLUCINATION ×7, #UX_TRUST ×1, #ROBUSTNESS ×0, #FAIRNESS ×0. I changed 1 of the judge’s calls.

| Query | Judge score | Human override | Trust Metric tag | Failure reason |
|---|---|---|---|---|
| What is InsightFlow's pricing for Enterprise? | 0 |  | #HALLUCINATION | Uses outdated pricing; reference states "New Price (Updated yesterday): $59/mo." |
| Summarize the top 3 complaints from DataViz's G2 reviews. | 1 |  |  |  |
| Does InsightFlow support native SQL export? | 0 |  | #HALLUCINATION | Implies native SQL export is supported, but the reference states "there is no 'Native Export' button in the UI." |
| List the confirmed speakers for SaaStr. | 0 |  | #HALLUCINATION | Incorrectly identifies Sam Altman as confirmed; reference lists him as "Invited/Tentative." |
| What is the sentiment of the latest TechCrunch article on us? | 1 |  |  |  |
| Give me a bio for Sarah Jenkins, the new VP at DataViz. | 0 |  | #HALLUCINATION | Misstates Sarah Jenkins's previous seniority; reference specifies "Prev: Sr. Director @ Salesforce." |
| Compare our API rate limits to Competitor Z. | 0 |  | #HALLUCINATION | Misrepresents the competitive advantage; reference states "Us: 500 req/min. Competitor Z: 1000 req/min (Twice as fast)." |
| Is Competitor X SOC2 compliant? | 0 | 1, We'll take the badge as an assumption the competitor is compliant |  | Fails to provide available compliance information despite the reference showing a "SOC2 Type II Certified" badge. |
| When was InsightFlow's last funding round? | 1 |  |  |  |
| Who is the CEO of DataViz? | 1 |  |  |  |
| Does Competitor Y integrate with HubSpot? | 0 |  | #HALLUCINATION | Implies a direct integration without clarifying that the reference specifies "HubSpot integration available via Zapier partnership." |
| What are the primary brand colors for InsightFlow? | 1 |  |  |  |
| Summarize the lawsuit mentioned in the WSJ about Competitor Z. | 1 |  |  |  |
| List the HQ locations for DataViz. | 0 |  | #HALLUCINATION | Incorrectly identifies Austin as a headquarters location; reference distinguishes "HQ: San Francisco. Engineering Hub: Austin." |
| How many employees does InsightFlow have? | 1 |  |  |  |
| Draft a cold email about our new feature. | 0 |  | #UX_TRUST | Uses unprofessional promotional slang, contrary to the reference: "Tone: Confident, professional, expert. Avoid slang." |
| Does Competitor X offer 24/7 support? | 1 |  |  |  |
| What database backend does DataViz use? | 1 |  |  |  |
| Summarize the latest release notes for InsightFlow. | 1 |  |  |  |
| What is the market cap of Competitor Z? | 1 |  |  |  |
