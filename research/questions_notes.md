# Notes on the Research Questions (not for pasting into claude.ai)

The questions themselves are in `questions.md`. That file is pasted as is into every floor, with a one-line request typed above it.
This file holds what the agent must not see before it checks: our own analysis, open issues and the history.
Drafted together with Claude, then chosen and edited by the group.

## Hooks (plain-language openings for the proposal)
- RQ1: Do developers who trust AI more check its code less?
- RQ2: Do reviewers judge code more harshly when they think AI wrote it?
- RQ3: Is AI-written web code less accessible to people with disabilities?

## Our own analysis
| | Type | Refuting result | Open issues |
|---|---|---|---|
| RQ1 | relationship | no correlation, or a positive one | — |
| RQ2 | causality | the same number of defect comments, or fewer, with the label | Direction must be justified in floor 4: automation bias predicts fewer comments, algorithm aversion predicts more. Hiding the purpose needs debriefing and ethics approval |
| RQ3 | relationship | the same number of violations, or fewer, in AI-generated forms | For floor 3: where the developer-written forms come from; automated checkers find only part of the accessibility problems |

Left for the design and measurement floors: the name of the trust questionnaire, the AI tools and versions, the accessibility checker.

## Change log
| Date | Version | Change |
|---|---|---|
| 2026-11-08 | 1 | First drafts checked by hand: not valid (undefined variables, missing population in RQ1 and RQ3). Definitions and populations added. |
| 2026-11-08 | 2 | Same ideas, shorter and simpler wording. Details moved to definitions. |
| 2026-11-08 | 3 | Floor 2 on claude.ai: RQ2 not valid, "bad practice" undefined (Q4). Removed it: a defect comment now points to a bug or a security problem. RQ1 and RQ3 valid with notes. |
| 2026-11-08 | 4 | Floor 2 on claude.ai: all three valid. Acted on its notes: RQ1 population (uses AI assistants) and professional developer defined; RQ2 control group, blinding and two raters stated; RQ3 hypothesis names the comparison group. Tool, questionnaire and checker names left for the design and measurement floors. |
| 2026-11-08 | 5 | Added a plain-language hook to each question. Formal questions reworded to be shorter and neutral (no direction in the question; the direction stays in H1). |
| 2026-11-08 | 6 | Final questions now use the simple hook wording, made neutral (no direction in the question). Population and details moved to the definitions. Must be rechecked with floor 2. |
| 2026-11-08 | 7 | Floor 2 on claude.ai (version 6): all three valid. Acted on its notes: each H0 is now the exact opposite of its one-sided H1; RQ2 raters do not know the group; RQ3 developers work without AI tools. Left for later floors: questionnaire, checker, AI tools and prompts, sample size, form size. |
| 2026-11-08 | 8 | Our constraints (access, participants, time, ethics) and the floor 2 status added at the end, so this one file is pasted into every floor. Questions unchanged. |
| 2026-11-08 | 9 | Constraints now say that this is a proposal: the study is planned, not run in the course. Questions unchanged. |
| 2026-11-08 | 10 | RQ3 definition: developer-written forms are now public solutions to one Frontend Mentor challenge, published on GitHub before 21 June 2022 (GitHub Copilot available to all), instead of recruited professional developers. Needs floor 2 and floor 3 again. |
| 2026-11-08 | 11 | Floor 2 (run 5) and floor 3 (run 3) on the new RQ3: valid. Floor 2 status line updated. Questions unchanged. |
| 2026-11-14 | 12 | The file is now three tables (questions and hypotheses, definitions, constraints) so it is easier to read. Wording unchanged. |
