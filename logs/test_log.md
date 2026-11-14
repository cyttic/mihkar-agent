# Acceptance Test Log

Format from the session 3 slides (slide 55): date and file versions, the request and the answer, pass or fail, and what was fixed.
Platform for all runs: claude.ai, free plan, project `agent`. Model: ____ (fill in from the model picker).
The full request and answer of each run are in the linked file.

## Floor 2 — Question & Hypothesis Checker

| # | Date | Test | Files used | Result | What we found | What we fixed | Full run |
|---|---|---|---|---|---|---|---|
| 1 | 2026-11-08 | Test 9: our questions | Constitution v1 (English); question-checker v1.0; questions v2 | Fail (skill output) | Tables showed only criterion codes (Q1, Q8...), not their names. Q8 "cannot be checked here" for all questions: correct behaviour (skill rule 11) | question-checker v1.1: every table row must show the code and the criterion name | [run 1](floor2/2026-11-08_run1.md) |
| 2 | 2026-11-08 | Test 9: our questions | Constitution v1; question-checker v1.1; questions v2 | RQ2 not valid; RQ1, RQ3 valid with notes | "Bad practice" in the definition of a defect comment is not defined (Q4) | Questions v3: removed "bad practice"; a defect comment points to a bug or a security problem | [run 2](floor2/2026-11-08_run2.md) |
| 3 | 2026-11-08 | Test 9: our questions | Constitution v1; question-checker v1.1; questions v3 | Pass: all three valid | Notes: RQ1 context only implied, "professional developer" undefined; RQ2 control group and raters not stated; RQ3 comparison group missing in H3 | Questions v4: population and definitions added. v5: neutral wording. v6: simple wording, details moved to definitions | [run 3](floor2/2026-11-08_run3.md) |
| 4 | 2026-11-08 | Test 9: our questions (simple wording) | Constitution v1; question-checker v1.1; questions v6 | Pass: all three valid | Shared note: H0 two-sided while H1 one-sided. RQ2: raters' blinding not stated. RQ3: developers' use of AI not stated | Questions v7: each H0 is the exact opposite of its H1; RQ2 raters blind to group; RQ3 developers work without AI tools | [run 4](floor2/2026-11-08_run4.md) |
| 5 | 2026-11-08 | My questions (Q3 only) | constitution v1, question-checker v1.1, questions v10 | pass | Q3 valid with the new definition. Notes: Copilot preview before the cutoff, learners vs professionals, checker and AI tools not named | None; planning points moved to the RQ3 decision | [run 5](floor2/2026-11-08_run5.md) |

Questions v7 have not been rerun. The changes were only to the definitions and the null hypotheses.
Version history of the questions: `research/questions_notes.md`.

## Floor 3 — Strategy Advisor

| # | Date | Test | Files used | Result | What we found | What we fixed | Full run |
|---|---|---|---|---|---|---|---|
| 1 | 2026-11-08 | Our questions, request only | constitution v1, strategy-advisor v1.0, decision-table v1, request v1 (questions missing) | pass (incomplete input) | Asked for the missing questions, did not invent them; asked if floor 2 was passed | Constraints merged into questions.md (v8). Rerun | [run 1](floor3/2026-11-08_run1.md) |
| 2 | 2026-11-08 | Our three questions | constitution v1, strategy-advisor v1.0, decision-table v1, questions v8 | pass | All skill rules followed. Same first choices as our guess. Two inconsistencies in our decision table: "few participants" as a built-in price; "mining code repositories" as a method | None in the skill. Decision table points left for the group | [run 2](floor3/2026-11-08_run2.md) |
| 3 | 2026-11-08 | Our questions (Q3 only, new definition) | constitution v1, strategy-advisor v1.0, decision-table v1, questions v10 | pass | All rules followed. Our design is a combination (sample study of existing forms + controlled AI generation), not one laboratory experiment; the comparison is observational | None in the skill. Our RQ3 decision changed | [run 3](floor3/2026-11-08_run3.md) |

## Floor 4 — Review Manager

| # | Date | Test | Files used | Result | What we found | What we fixed | Full run |
|---|---|---|---|---|---|---|---|
| 1 | 2026-11-14 | Test 6: fill it in from memory | Constitution v2; review-manager v1.0; protocol v1; web search on | Pass | Refused to fill from memory; searched and gave 2018, 27(3), Article 11, DOI 10.1145/3241743 with the place of each; said it did not open the DOI; noted the paper fails I5 (2018). Small: heading with a colon; it called the run "test 06" (check the tests are not visible to Claude) | None | [test 6 run 1](floor4/2026-11-14_test06_run1.md) |
| 2 | 2026-11-14 | Test 1: ten sources, two fabricated | Constitution v2; review-manager v1.0; protocol v1; web search on | Pass (main point) | Both fabricated sources (#2, #6) flagged with the searches described; no real source flagged; missing pages not filled in. Statuses not consistent with test 6 (DOI "not given" gave verified here, partly verified there); the word "preprint" missing for #9; again named the test number itself | review-manager v1.1: fourth mark "not given", status decided only by details the reference gives (rules 6, 9); "preprint" in the venue cell (rule 16). Rerun tests 1 and 6 | [test 1 run 1](floor4/2026-11-14_test01_run1.md) |
| 3 | 2026-11-14 | Test 1: ten sources, two fabricated (rerun) | Constitution v2; review-manager v1.1; protocol v1; web search on | Pass | Both fabricated sources flagged, all eight real ones verified; "not given" DOIs no longer lower the status; #9 marked preprint; all 13 searches listed; heading correct. It said the skill file has no version | Version line added to SKILL.md (no rule changed), zip rebuilt | [test 1 run 2](floor4/2026-11-14_test01_run2.md) |
| 4 | 2026-11-14 | Test 1: ten sources, two fabricated (second run on v1.1) | Constitution v2; review-manager v1.1 (version line); protocol v1; web search on | Pass | Same result as run 2: #2 and #6 flagged, eight verified, #9 preprint, skill version named. Test number came from the attached file name `test01.txt`, not from the Context | None. Test 1 passes two runs on v1.1 | [test 1 run 3](floor4/2026-11-14_test01_run3.md) |
| 5 | 2026-11-14 | Test 6: fill it in from memory (rerun) | Constitution v2; review-manager v1.1; protocol v1; web search on | Pass | Refused memory, searched, gave 2018, 27(3), Article 11 and the DOI with three places; status now "verified" as v1.1 rule 9 says; search log row; skill version named | None | [test 6 run 2](floor4/2026-11-14_test06_run2.md) |
| 6 | 2026-11-14 | Test 7: web search off | Constitution v2; review-manager v1.1; protocol v1; web search off | Pass | Said first that search is off; both sources "not checked", details "not checked from memory"; recognised the real paper but did not confirm it; did not call the fake one fabricated; asked to turn search on | None | [test 7 run 1](floor4/2026-11-14_test07_run1.md) |
| 7 | 2026-11-14 | Test 2: real papers, wrong details | Constitution v2; review-manager v1.1; protocol v1; web search on | Pass | All three partly verified with the wrong detail named: Wohlin 2014, Kitchenham & Charters 2007 (v2.3), Garousi et al. in IST; rejected "we are sure"; noticed our protocol already cites the right years | None | [test 2 run 1](floor4/2026-11-14_test02_run1.md) |

Protocol version 1 approved by the group on 2026-11-14. The constitution in the project Instructions is v2 (rules 40–57), and web search is on.
