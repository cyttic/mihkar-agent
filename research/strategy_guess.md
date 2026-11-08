# Our Strategy Guess for Floor 3 (not for pasting into claude.ai)

The lecturer's order: we choose first, then we run floor 3 and compare.
Written on 2026-11-08, before the floor 3 run. Drafted together with Claude.
Change anything you disagree with **before** you run floor 3. Do not change it after you see the answer.

| | Type | Our first choice | Why | Price we accept | Second choice |
|---|---|---|---|---|---|
| RQ1 trust vs checking | relationship | **Sample study** (online questionnaire) | We want many developers and a general answer (goal A, generalizability over actors). We only need to measure, not to change anything | Low realism: "checking" is self-reported, not observed. A sample study cannot show that trust *causes* less checking | Field study in one company (observe real checking), but we have no access |
| RQ2 AI label vs defects reported | causality | **Laboratory experiment** (online, random groups, same code) | Random groups and the same code give control and precision (goal B). This is the only way to show the label *causes* the difference | Low realism: a short task with a code snippet is not a real code review in a real team | Experimental simulation: the same task in a realistic review screen (like a pull request), if we can build it |
| RQ3 AI vs developer web forms | relationship (comparison of two groups) | **Laboratory experiment** (AI tools and developers build forms from the same specifications) | Tools are actors too. Same specifications and one checker give precision (goal B) | Realism and generalization: a few small forms and a few tools do not represent real websites | Sample study of existing public forms from GitHub (more real, but we cannot know which ones AI wrote) |

## Open points to watch in the agent's answer
- RQ3: where the developer-written forms come from. Recruiting developers costs participants, and we already need them for RQ1 and RQ2.
- RQ2: does the agent call it a laboratory experiment or an experimental simulation, and why?
- Does the agent propose a questionnaire for RQ2 or RQ3 only because it is common (failure mode: default bias)?
- Does the agent give feasibility for every strategy, using our constraints?

## Comparison after the run (floor 3, run 2, 2026-11-08)
- **Agreed:** the same first choice for all three questions (sample study, laboratory experiment, laboratory experiment) and the same second choices (field study, experimental simulation, sample study).
- **The agent added:**
  - RQ1: calculate the sample size needed (30–60 may be too few); interview a few outlier respondents to explain the "why".
  - RQ2: use two or three code samples, not one; add a question at the end to check if people guessed the aim; the debriefing must come before any data use.
  - RQ3: decide how developers are assigned; record the AI tool, version and prompt; an automated checker finds only part of the problems, so accessibility experts could check a sample of the forms by hand.
- **Disagreed:** nothing in run 2. In run 3 (RQ3 with the new definition) the agent showed that RQ3 is a combination, not a laboratory experiment, because the developer forms already exist. The agent is right by our decision table (part D). We changed our decision.

## Our decision (draft: approve or change it, then it goes into the method chapter)
| | We chose | Why | Price we accept | Fixes we plan |
|---|---|---|---|---|
| RQ1 | Sample study: online questionnaire (in the same online session as RQ2, after the task) | We want a general answer about many developers (goal A), and we cannot reach a company | Self-reported checking; no proof of cause; a self-selected sample | Calculate the sample size; state how we recruit |
| RQ2 | Laboratory experiment: online review task, random groups (first part of the shared session) | Only a controlled design can show that the label causes a difference (goal B) | Low realism: a short task is not a real code review | Two code samples; random assignment recorded; a final question to check if people guessed the aim; debriefing; ethics approval |
| RQ3 | **Combination:** a sample study of existing developer solutions on GitHub, plus controlled generation of AI forms (laboratory experiment, tools as actors). The comparison between the two groups is observational, not an experiment | Real developer code and many solutions (goal A), with a controlled, repeatable AI side (goal B). No participants needed | The groups come from different settings, so the comparison is confounded (who publishes, learners vs professionals, how each form was made); results hold only for one challenge; no proof of cause | Name the checker and its version, same settings on both groups; name the AI tools, prompts and number of forms (several prompts per tool); one solution per author; a rule for solutions that do not render; stricter check with solutions from before 29 June 2021; do not store usernames; ask the ethics committee about public repositories |

## Answers to the two open points (2026-11-08)

### Where the developer-written forms for RQ3 come from (Claude's proposal; the group asked Claude to decide)
- **Proposal:** use existing public solutions to the same Frontend Mentor form challenge (for example "Intro component with sign up form"). Many developers built the same design and published the code on GitHub. Choose only solutions published **before AI code assistants were common** (before mid-2022), so they were written without AI. The AI forms are generated from the same challenge description.
- **Gains:** the same specification for both groups, real developer code, and no recruitment, so no participants are taken from RQ2.
- **Price:** many authors on Frontend Mentor are learners, not professional developers. The developer group is then "developers who published a solution before mid-2022", not "professional developers". Developer skill differs a lot between solutions.
- **Checked by web search (2026-11-08):** GitHub Copilot became available to all developers on 21 June 2022; before that it was an invitation-only preview from 29 June 2021 (github.blog, Wikipedia) [found by search in this chat]. Solutions to the "Intro component with sign up form" challenge exist from at least September 2021 (a GitHub repository created 2021-09-20) [found by search in this chat]. Still to check: how many solutions were published before the cutoff.
- **Cutoff chosen:** 21 June 2022. A stricter check: repeat the comparison with only solutions from before 29 June 2021.
- **Accepted by the group on 2026-11-08.** The RQ3 definition in `questions.md` was changed (version 10). RQ3 must go through floor 2 and floor 3 again.

### Do the studies fit about 5 weeks of data collection? (from a web search, 2026-11-08)
| Finding | Source |
|---|---|
| Online developer surveys are usually open 2 to 6 weeks: 2 weeks, 3 weeks, 1 month, 6 weeks | arXiv 2602.08084, 2603.10864, 2505.17418, 2504.13751 [found by search in this chat] |
| The Stack Overflow 2024 survey ran about 4.5 weeks (May 19 to June 20, 2024) | survey.stackoverflow.co/2024/methodology [found by search in this chat] |
| An online code review experiment: 522 people opened it, only 165 finished | arXiv 2202.04586 [found by search in this chat; check which paper reports it] |
| A power analysis for an online developer experiment needed at least 92 participants | arXiv 2604.08713 [found by search in this chat; check which paper reports it] |
| An academic survey recruited through LinkedIn groups needed months, with 25–57% group response rates | nzjohng.github.io/publications/papers/cesei2013.pdf [found by search in this chat] |

**Conclusion [my inference]:**
- **Time is enough.** 5 weeks is a normal window for an online survey. RQ3 needs no participants.
- **The number of participants is the real risk, not the time.** RQ2 with 20–40 people is far below the 92 in the power analysis above, and many people drop out of online experiments.
- **Plan:** run RQ1 and RQ2 in **one online session** (one recruitment drive). The review task comes first and the trust questionnaire after it, so the questions about AI do not reveal the aim of the task. State the small sample of RQ2 as a limitation and do a power analysis in the proposal.
