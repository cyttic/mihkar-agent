# Update Log

Every change to the agent, its files or our research decisions gets one row: date and time, what changed and why,
which floor, the new version, and which tests were run and which were not.
This follows the lecturer's own agent (session 3: "work status document, with an update log"; session 4: "the fix is
recorded in the update log"; in the session 4 lecture he showed his log: the fix, the date, the version number and
the floor). The current state of everything is in `work_status.md`. Pass or fail of each test run is in `test_log.md`.

Upload this file and `work_status.md` to the project Context, and upload them again after every new row.

| Date and time | Floor | Change and reason | New version | Tests run | Tests not run |
|---|---|---|---|---|---|
| 2026-11-04 13:40 | 1, 2 | First version of the agent, in Hebrew: constitution, question-checker skill, floor 2 requirements, floor 1 and floor 2 tests | constitution v1 (he), question-checker v1.0 | — | all |
| 2026-11-08 | all | Agent rewritten in English (approved by the lecturer), short and plain sentences | constitution v1, question-checker v1.0 | — | — |
| 2026-11-08 | 2 | Floor 2 tables showed only criterion codes. Every row must show the code and the criterion name (test log, floor 2 run 1) | question-checker v1.1 | floor 2 test 9, runs 1–2 | floor 2 tests 1–8 |
| 2026-11-08 | — | Research questions versions 1–11: definitions, populations, neutral wording, H0 as the exact opposite of H1, constraints added, new RQ3 definition. Full history in `research/questions_notes.md` | questions v11 | floor 2 runs 2–5; floor 3 runs 1–3 | — |
| 2026-11-08 20:28 | 3 | Floor 3 added: strategy-advisor skill with the group's decision table, requirements, 11 tests | strategy-advisor v1.0, decision-table v1 | floor 3 own questions, runs 1–3 | floor 3 tests 1–11 |
| 2026-11-08 | — | RQ3 decision changed after floor 3 run 3: a combination of a sample study and controlled AI generation, not one laboratory experiment (`research/strategy_guess.md`) | — | — | — |
| 2026-11-14 20:15 | — | `research/questions.md` turned into three tables (questions, definitions, constraints), easier to read. Wording unchanged | questions v12 | none needed (no content change) | — |
| 2026-11-14 20:15 | 4 | Floor 4 added: review-manager skill with the group's review protocol, requirements, 8 own tests (test 9 is the lecturer's list) | review-manager v1.0, protocol v1 | — | floor 4 tests 1–9 |
| 2026-11-14 20:15 | — | Verification exercise of session 4: the three labelled claims (slides 35, 38, 39) checked against the papers. Claim 1 partly correct, claim 2 partly correct (seven questions, not four), claim 3 correct (`research/claims_check_session4.md`) | — | — | — |
| 2026-11-14 20:40 | 4 | Review protocol approved by the group | protocol v1 (approved) | — | floor 4 tests 1–9 |
| 2026-11-14 20:50 | 2, 3 | Skill descriptions shortened to under 200 characters with no colon (the lecturer's rule for the free plan, session 4 lecture). Rules unchanged | question-checker v1.2, strategy-advisor v1.1 | — | a quick rerun of one test per floor, to confirm the skills still load |
| 2026-11-14 20:50 | 1 | Constitution: floors list added (rules 40–43, the lecturer asked to update the constitution with every floor); missing chapters from the session 4 checklist added: methodological rules, reproducibility and documentation, the structure of every answer (rules 44–57). Rule 52: a summary for this log at the end of every stage | constitution v2 | — | floor 1 tests 1–10 again, at least the ones on sources and flattery |
| 2026-11-14 20:50 | — | Update log (this file) and work status document added, following the lecturer's log component. Research idea document added to the Context upload list | — | — | — |
| 2026-11-14 21:10 | 4 | First floor 4 run: test 6 (fill in from memory). Pass, no change to the skill | — | floor 4 test 6, run 1 | floor 4 tests 1–5, 7–9; test 6 run 2 |
| 2026-11-14 23:25 | 4 | Test 1 run 1: pass on the main point. Its statuses did not agree with test 6 (a missing DOI gave "verified" here, missing year and DOI gave "partly verified" there). SKILL.md rules made exact: fourth mark "not given" (rule 6), status decided only by the details the reference gives (rule 9), "preprint" written in the venue cell (rule 16). Zip rebuilt | review-manager v1.1 | floor 4 test 1, run 1 | tests 1 and 6 again with v1.1; tests 2–5, 7, 8 |
| 2026-11-14 23:45 | 4 | Test 1 run 2 with v1.1: pass. The answer said the skill file states no version, so a version line was added to SKILL.md (no rule changed). Zip rebuilt | review-manager v1.1 (version line) | floor 4 test 1, run 2 | test 1 again with v1.1 (second pass on the same version); test 6 with v1.1; tests 2–5, 7, 8 |
| 2026-11-14 23:55 | 4 | Test 1 run 3 with v1.1: pass. Test 1 now passes two runs on the same version. No change | review-manager v1.1 | floor 4 test 1, run 3 | test 6 with v1.1 (two runs); tests 2–5, 7, 8 (two runs each) |
| 2026-11-15 00:05 | 4 | Test 6 run 2 with v1.1: pass, status now "verified" as the fixed rule 9 says. No change | review-manager v1.1 | floor 4 test 6, run 2 | test 6 once more on v1.1; tests 2–5, 7, 8 |
| 2026-11-15 00:20 | 4 | Test 7 run 1 (web search off) with v1.1: pass. No change | review-manager v1.1 | floor 4 test 7, run 1 | second runs of tests 6 and 7; tests 2–5, 8 |
| 2026-11-15 00:35 | 4 | Test 2 run 1 with v1.1: pass. No change | review-manager v1.1 | floor 4 test 2, run 1 | second runs of tests 2, 6, 7; tests 3–5, 8 |
