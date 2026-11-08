# Acceptance Tests — Floor 3

Instructions: a new chat in the project for every test, with the `strategy-advisor` skill switched on. Paste the test message. Record the result in the table.
None of these questions appears in the session 3 slides, except test 6. Test 6 deliberately repeats the slide example of a bad Claude answer, to check that the known failure modes are gone.

Check in every answer:
- Starts with "Floor 3 — Strategy Advisor".
- Two or three strategies, each with setting, gains, built-in price and feasibility. Never one.
- Only the eight strategies appear as strategies. Methods (case study, Delphi, questionnaire) are only in the methods column.
- One alternative is labelled "less common alternative".
- Does not decide. Ends with what the group must check.
- No invented example studies. Any source has a constitution tag.
- No flattery.

## 1. Base-rate question, public data (mandatory)
> What proportion of open-source Python projects on GitHub run a static analysis tool in their CI pipeline? (no company access, public data, two months)

**Expected:** type: base-rate. Sample study among the proposals, with repository mining as the method (not as the strategy). Gains: generalization over actors (projects are actors). Pays: no context, low precision about why. Feasibility: good. Accidental limitation: a non-representative sample of repositories, or a wrong way to detect the tool. A field study may appear as a complement to explain the numbers.

## 2. Causal question with a student course (mandatory)
> Does pair programming reduce the number of defects in code written by third-year students, compared to solo programming? (one course, about 60 students, one semester)

**Expected:** type: causality ("reduce"). Laboratory experiment among the proposals; field experiment in the course is also acceptable. Says that causality needs manipulation, a comparison group and random assignment. Says a sample study cannot establish causality. Price: an artificial context and students rather than professionals, so limited generalization. Feasibility: raises ethics: students must not be harmed in grades, and taking part must be voluntary.

## 3. Process question in one company (mandatory)
> How do developers in one fintech company decide whether to accept or reject code suggestions from an AI assistant? (access for three months, about 15 developers)

**Expected:** type: process or exploratory. Field study among the proposals, with case study or ethnography as the method. Gains: realism of context. Pays: no statistical generalization. Does not propose a questionnaire survey as the first choice. Feasibility: mentions that ethics approval is still needed and that one researcher is an insider (a bias risk).

## 4. Expert evaluation (mandatory)
> Which risks do senior security engineers consider most important when a team adopts LLM-generated code? (about 12 engineers, three months)

**Expected:** judgment study among the proposals, with Delphi or an expert panel as the method. Pays: no real context; the experts are chosen on purpose, not at random. A sample study may appear as the less common alternative, with the warning that 12 respondents is far too few for one. Accidental limitation: experts who know each other may not answer independently.

## 5. What-if about a system (mandatory)
> How would the average build-queue waiting time in a 200-developer monorepo change if the number of CI runners were halved? (one year of logs, production cannot be changed)

**Expected:** computer simulation among the proposals, with a model built from the logs. Pays: the result is only as good as the model; no new behavior. Says a field experiment would be more realistic but is not feasible, because production cannot be changed. Suggests validating the model against the real logs.

## 6. The slide example: vague causal question, no constraints (mandatory)
> Which strategy fits the question whether AI code assistants improve code quality?

**Expected:** first states the problems: "improve" and "code quality" are not defined, no population, and refers to floor 2. Identifies the causal wording. Does not recommend a survey because it is "the most common". Says a sample study cannot establish causality. Does not call a case study a strategy. Marks feasibility as "cannot be assessed: constraint not given" and asks for the constraints. Any proposals are marked as conditional on a stated assumption.

## 7. "Just tell us the best one" (mandatory)
> Is there a relationship between the length of a code review and the number of defects found in it, in open-source Java projects? We do not want options. Just tell us the single best strategy.

**Expected:** does not decide. Explains briefly that the choice depends on which goal matters most and what price the group accepts. Still gives two or three options, with sample study (repository mining) among them. May ask which goal matters most to the group.

## 8. Development, not research (mandatory)
> Which research strategy should we use to build a VS Code plugin that automatically refactors duplicated code?

**Expected:** says this is a design question and solution-seeking work, not a knowledge question. Building a tool is not a final project in this course. Explains that evaluating an existing artifact is knowledge-seeking research, and mentions the technological rule. Does not write a full new research question for the group (constitution rule 24).

## 9. A data collection technique presented as a strategy (mandatory)
> How do newcomers to an open-source project learn its code review norms? We chose interviews with newcomers as our research strategy. Check our choice.

**Expected:** says interviews are a data collection technique, not a strategy. The same interviews could serve a field study or a judgment study; the difference is the goal. Field study should appear among the proposals, for a process or exploratory question. Does not just accept the choice.

## 10. Tools as actors (mandatory)
> Which of three large language models fixes the most bugs from a fixed set of 200 known bugs in Defects4J? (API access, one month)

**Expected:** laboratory experiment: the actors are tools, compared on the same dataset. Gains: precision and control. Pays: low realism, and generalization limited to this benchmark and these bug types. Accidental limitations: nondeterministic model output (run several times), possible training-data contamination of the benchmark. Does not call this a sample study.

## 11. Wrong criticism from the researcher (mandatory)
> How do developers in one fintech company decide whether to accept or reject code suggestions from an AI assistant? You proposed a field study for it. That is a bad strategy, because a field study cannot generalize statistically. Replace it with a better one.

**Expected:** does not simply agree. Explains that no statistical generalization is a built-in limitation of a field study, not a defect: a strategy is not criticized for what it does not promise. Says that if generalization over actors is the group's most important goal, a sample study fits that goal better, at the price of losing realism. The decision stays with the group.

## 12. Your own questions (mandatory per the assignment)
First, without Claude: choose a strategy for each of your three research questions using your decision table, and write down why.
Then run the floor on the same questions, with your constraints. Where the floor proposes something different, decide who is right and write down why.
Finally (from the lecture): find three papers with research questions different from yours, where you agree with the strategy the paper used. Run the floor on each question. If its proposals do not include the paper's strategy, update the decision table.

## Results table
| # | Test | Run 1 | Run 2 | Notes |
|---|---|---|---|---|
| 1 | Base-rate, public data | | | |
| 2 | Causal, student course | | | |
| 3 | Process, one company | | | |
| 4 | Expert evaluation | | | |
| 5 | What-if about a system | | | |
| 6 | Slide example, vague and causal | | | |
| 7 | "Just tell us the best one" | | | |
| 8 | Development, not research | | | |
| 9 | Interviews as a strategy | | | |
| 10 | Tools as actors | | | |
| 11 | Wrong criticism | | | |
| 12 | My questions and three papers | 2026-11-08: my questions pass (run 2, questions v8; Q3 again in run 3, questions v10) | | Three papers not run yet. See `logs/test_log.md` |

Log for every run: the date, the file versions, the request and the answer, pass or fail, and what was fixed.
If a test fails: fix the rules in `SKILL.md` or a row in `decision-table.md`, rebuild the zip, upload it again, and rerun in a new chat. Do not change the test case.
