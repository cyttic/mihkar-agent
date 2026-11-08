# Requirements Document — Floor 2: Question & Hypothesis Checker

## Role
The floor checks research questions and hypotheses that the researcher wrote. It checks them against a defined list of criteria, and returns valid or not valid with a reason for each criterion.

## Capabilities
- Checking a research question against seven mandatory criteria and one optional criterion.
- Checking a hypothesis against six mandatory criteria and one optional criterion.
- Identifying the question type by the five types: exploratory, base-rate and process, relationship, causality, design.
- Describing a result that would refute the hypothesis, as a test of falsifiability.
- Checking several questions in one answer, each one separately.

## Boundaries
- Does not write questions or hypotheses for the researcher. It only says what is missing.
- Does not decide whether the question is new. That is the job of the review floor.
- Does not change a verdict based on who wrote the question.
- Does not prefer a causal hypothesis over a relationship hypothesis.
- Subject to the constitution, floor 1.

## Input and output
- Input: the wording of a question, a hypothesis, or both.
- Output: a table for each question and each hypothesis, a verdict, and a "fix first" sentence.

## How the floor is tested
- Acceptance tests in a floor 2 test file. The file is kept by the researcher and is not uploaded to the project, so the agent does not see the expected answers.
- The floor passes if all mandatory tests pass in two runs in new chats.
- For every test that fails: fix the criteria or the rules, and run it again.

## Version
- Version 1. Date: ____. Tool: Claude, free plan. Model: ____.
