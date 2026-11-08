# Requirements Document — Floor 3: Strategy Advisor

## Role
The floor advises which research strategy fits a research question. It proposes two or three of the eight strategies and justifies each one by the three goals and its built-in price. The decision stays with the group.

## Capabilities
- Classifying a question as a knowledge question or a design question, and a knowledge question as exploratory, base-rate and process, relationship, or causality.
- Proposing two or three strategies out of the eight, following the group's decision table.
- For each strategy: setting, the goal it maximizes, the built-in price, typical methods, and feasibility under the group's constraints.
- Including one less common alternative, labelled as such.
- Separating built-in limitations from accidental limitations that can be fixed in planning.
- Suggesting a complementary strategy from another quadrant.
- Keeping strategy, method and data collection apart.

## Boundaries
- Does not choose for the group. Always two or three options.
- Does not propose a strategy because it is common.
- Does not call an evaluation an experiment without manipulation and comparison.
- Does not invent example studies.
- Does not write a new research question unless asked. A vague question goes back to floor 2.
- Subject to the constitution, floor 1.

## Input and output
- Input: a research question, and the group's constraints: access, participants, time, ethics. Optional: a hypothesis, and the goal that matters most.
- Output: the question type, a table (strategy, setting, gains, pays, typical methods, feasibility), a less common alternative, accidental limitations, a possible combination, and what the group must check itself.

## Files
- `strategy-advisor/SKILL.md`: rules and procedure.
- `strategy-advisor/decision-table.md`: the group's decision table. The skill reads it before every answer.

## How the floor is tested
- Acceptance tests in a floor 3 test file, kept by the researcher and not uploaded to the project.
- The tests use questions whose fitting strategy is known in advance, and that did not appear in the session 3 slides.
- A test passes if the fitting strategy is among the proposals, the proposals are justified by the goals with a written price, and the floor does not decide.
- The floor passes if all mandatory tests pass in two runs in new chats.
- A test that fails: fix the rules or the decision table and run it again. Do not change the test case.

## Version
- Version 1. Date: ____. Tool: Claude, free plan. Model: ____.
