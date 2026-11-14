# Work Status

The current state of the agent and of our research. Updated after every change (each change also gets a row in
`update_log.md`). Upload to the project Context together with the update log.

Last update: 2026-11-15 00:35.

## The agent, component by component (the five components, session 3)

| Component | Where it lives in Claude | Current version | Status |
|---|---|---|---|
| Constitution (floor 1) | Project Instructions | v2 (2026-11-14) | Rules 40–57 added. Must be pasted again into Instructions. Floor 1 tests to rerun |
| Floor 2, question-checker | Skill in every member's account | v1.2 (2026-11-14) | Tested on our questions. Description shortened: upload the new zip again |
| Floor 3, strategy-advisor + decision table | Skill in every member's account | v1.1 + decision table v1 | Tested on our questions. Description shortened: upload the new zip again. The three-papers part of test 12 is not done |
| Floor 4, review-manager + protocol | Skill in every member's account | v1.1 + protocol v1 (approved 2026-11-14) | Test 1 done (two passes on v1.1). Tests 2, 6 and 7 passed once on v1.1: one more run each. Tests 3–5, 8 not run. Needs web search on |
| Knowledge files | Project Context | — | Syllabus; requirements of floors 2–4; research idea document; this file; update log |
| Acceptance tests | Our repository only (never in Context) | — | Floor 1, 2, 3 tests written; floor 4 tests 1–8 written, test 9 waits for the lecturer's list |
| Log | Test log and full runs: repository. Update log and work status: repository and Context | — | Up to date |

## Our research

| | Question | Strategy (our decision) | Status |
|---|---|---|---|
| RQ1 | Is developers' trust in AI related to how much of its code they check? | Sample study, online questionnaire | Passed floors 2 and 3. Literature review next (floor 4, review question RV1) |
| RQ2 | Do reviewers report a different number of defects when code is labelled as AI-generated? | Laboratory experiment, online, random groups | Passed floors 2 and 3. The direction of H2 must be justified from the literature (RV2: automation bias vs algorithm aversion) |
| RQ3 | Is AI-written web code more or less accessible than code written by developers? | Combination: sample study of public developer solutions + controlled AI generation | Passed floors 2 and 3 (new definition). Review question RV3, with grey literature |

## Open work, by deadline

| Due | What | Status |
|---|---|---|
| Session 5 | Present: research problem, questions, hypotheses and null hypotheses, and a working floor 1 (what we wrote, what was fixed, what we agreed with the agent) | Research idea document ready |
| Session 5 | Table of the three claims in the session 4 slides | Done (`research/claims_check_session4.md`) |
| Session 5 | Review protocol | Done, approved |
| Session 5 | Floor 4 passes the acceptance test (the lecturer's list of ten sources, two fabricated) | Waiting for the list |
| Session 5 | Verification table for every source we found | Not started: run the searches first |
| Session 5 | Choose one empirical paper from our review for the critique after session 5 | Not started |
| First control meeting (after session 6) | Tool capabilities table with sources and reliability ratings; one-page requirements document for the whole agent (session 1 tasks) | Not in the repository: check whether we made them |
