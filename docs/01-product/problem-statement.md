# Problem Statement

## 1. Background

Job seekers who are targeting international roles often need to monitor multiple job sources, evaluate a large number of postings, compare each role with their experience, prepare tailored application materials, submit applications, and keep track of application status.

This process is repetitive, fragmented, time-consuming, and difficult to manage consistently.

## 2. Problem

The job-search process lacks a single, reliable workflow that can continuously identify relevant opportunities, remove unsuitable jobs using explicit rules, evaluate the remaining opportunities against a candidate profile, prepare application materials, and maintain an accurate application history.

As a result, a candidate may:

- Miss newly published opportunities because job sources are checked manually.
- Spend time reviewing jobs that do not satisfy basic requirements.
- Apply inconsistently because each application requires repeated research and preparation.
- Lose track of which jobs were reviewed, shortlisted, applied to, or rejected.
- Find it difficult to understand why a job is considered a strong or weak match.
- Repeat work because the same job can appear across multiple sources.
- Depend on a single AI provider whose availability or quota may change.

## 3. User Problem

The target user needs to focus on high-value decisions—such as whether a role is worth pursuing—rather than repeatedly performing mechanical search, filtering, comparison, preparation, and tracking tasks.

The system should therefore act as an **AI-assisted job-search and application agent**, not as an uncontrolled autonomous applicant.

## 4. Proposed Solution

The solution will provide a Telegram-first workflow that:

1. Collects and maintains the candidate's job-search profile and preferences.
2. Discovers recent opportunities from permitted public or official job sources.
3. Normalizes job information into a consistent structure.
4. Applies deterministic eligibility filters before using generative AI.
5. Uses AI to evaluate candidate-job fit and explain the recommendation.
6. Detects and prevents duplicate job processing.
7. Prioritizes the strongest opportunities for review.
8. Prepares tailored application materials when appropriate.
9. Requests human approval before consequential application actions.
10. Records job and application status in a persistent database.
11. Reports relevant new opportunities and application activity through Telegram.
12. Uses an LLM fallback strategy so the workflow is not dependent on a single provider.

## 5. Key Business/Process Pain Points

| Pain Point | Impact |
|---|---|
| Manual multi-source searching | High time consumption |
| Too many irrelevant postings | Low search efficiency |
| Repeated job evaluation | Unnecessary effort |
| Duplicate postings | Wasted review/application effort |
| Manual tailoring of applications | Slow application throughput |
| Weak application tracking | Missed follow-ups and poor visibility |
| Opaque AI recommendations | Low trust in automation |
| Single-provider AI dependency | Reliability risk |

## 6. Desired Outcome

The desired outcome is a controlled, auditable workflow in which the candidate receives a small number of high-quality, explainable job opportunities instead of manually processing a large volume of postings.

The system should reduce repetitive work while keeping the candidate in control of decisions that can create professional or external consequences.

## 7. Success Definition

The problem is considered meaningfully addressed when the MVP can reliably demonstrate the following end-to-end flow:

**Discover → Filter → Deduplicate → Match → Rank → Prepare → Human Approval → Track → Report**

The MVP does not require unrestricted autonomous application submission. Its primary objective is to demonstrate reliable AI-assisted decision support and workflow automation.