# mihkar-agent — research agent for "Research Methods in Software Engineering"

A Claude research agent that helps plan **empirical research in software engineering**, built floor by floor
during the course (13 floors, one per week). The agent does the technical work; the researcher chooses,
decides and is responsible for every claim, number and source.

- **Platform:** Claude (free plan), one Claude **Project** plus **Skills**.
- **Language of the agent:** English, short and plain sentences (approved by the lecturer).
- **Status (8 November 2026):** floors 1–3 are built (constitution, question & hypothesis checker, strategy advisor).
  Our three research questions passed floor 2 and floor 3, and the two-page research idea document is drafted.
  Floors 4–13 follow the course.

## Our research

Topic: trust, fairness and accessibility in AI-written code. The course only plans the study: the product is a
research proposal, no data is collected.

| | Question | Strategy (floor 3) |
|---|---|---|
| RQ1 | Is developers' trust in AI related to how much of its code they check? | Sample study (online questionnaire) |
| RQ2 | Do reviewers report a different number of defects when code is labelled as AI-generated? | Laboratory experiment (two random groups) |
| RQ3 | Is AI-written web code more or less accessible than code written by developers? | Combination: sample study of public developer solutions + controlled AI generation |

The hypotheses, definitions and constraints are in `research/questions.md`. The reasoning and the price of each
strategy are in `research/strategy_guess.md` and in the research idea document (`research/research_idea.pdf`).

## Repository layout

```
constitution.md                 Floor 1: the constitution → paste into the Project "Instructions"
floor2/
  question-checker/SKILL.md     Floor 2: the skill source (criteria and procedure)
  question-checker.zip          Floor 2: the zip to upload to Claude (built from the folder above)
  requirements_floor2.md        Floor 2: requirements document → upload to the Project "Context"
floor3/
  strategy-advisor/SKILL.md     Floor 3: the skill source (rules, procedure, answer template)
  strategy-advisor/decision-table.md  Floor 3: the group's decision table (the skill reads it)
  strategy-advisor.zip          Floor 3: the zip to upload to Claude
  requirements_floor3.md        Floor 3: requirements document → upload to the Project "Context"
tests_to_paste/
  floor1/test01.txt … test10.txt   acceptance tests, ONLY the message to paste into a chat
  floor2/test01.txt … test08.txt
  floor3/test01.txt … test11.txt
research/
  questions.md                  our three research questions and our constraints → the one file to paste into every floor (type a one-line request above it)
  questions_notes.md            our own analysis, hooks and change log (never paste it into claude.ai)
  strategy_guess.md             our own strategy choice (written before the floor 3 run), the comparison and our decision (never paste it)
  research_idea.html            the two-page research idea document (source; edit this one)
  research_idea.pdf             the same document as PDF, for the first control meeting
logs/
  test_log.md                   the acceptance test log: date, files, result, what was fixed (one row per run)
  floor2/2026-11-08_runN.md     full request and answer of each floor 2 run
  floor3/2026-11-08_runN.md     full request and answer of each floor 3 run
answers_keep_private/
  floor1_expected.md            expected behaviour + results table for floor 1 (never give to the agent)
  floor2_expected.md            expected behaviour + results table for floor 2 (never give to the agent)
  floor3_expected.md            expected behaviour + results table for floor 3 (never give to the agent)
```

| Floor | Name | Type | File |
|---|---|---|---|
| 1 | Constitution | Project instructions | `constitution.md` |
| 2 | Question & Hypothesis Checker | Skill `question-checker` | `floor2/` |
| 3 | Strategy Advisor | Skill `strategy-advisor` + decision table | `floor3/` |
| 4 | Review Manager | Skill | coming |

## Installation (once)

The three steps follow the lecturer's slide "where each part of the agent lives in Claude".

### 1. Turn on code execution (once per account)
claude.ai → **Settings** → **Capabilities** → turn on **Code execution and file creation**.
Without it, skills do not work, even if they are uploaded.

### 2. Create the Project
1. **Projects** → **New project** → name it `agent`.
2. **Instructions** → paste the **whole text** of `constitution.md` → save.
3. **Context** (called "Project knowledge" on the slide) → upload:
   - `floor2/requirements_floor2.md` and `floor3/requirements_floor3.md` (fill in the date and model in
     their last section first),
   - the course syllabus from Moodle.

Context holds only what the agent needs to work. **Never** put test files or `answers_keep_private/` there:
the agent would see the expected answers. The free plan allows up to 5 projects.

### 3. Install the skills
claude.ai → **Customize** → **Skills** → **Create skill** → **Upload a skill** → choose
`floor2/question-checker.zip` → make sure the skill is **switched on**. Do the same for
`floor3/strategy-advisor.zip`.

Skills belong to the account, not to the project, so they work in every chat.

## Usage

1. Open the `agent` project → **New chat**. Use a new chat for every lesson; long old chats run out of memory.
2. Write your request in English. Skills are picked automatically from the request, for example:
   > Check the following research question and hypothesis: …
3. Every answer starts with the active floor, e.g. "Floor 2 — Question & Hypothesis Checker".
4. The agent checks your work; it does not write research questions or hypotheses for you unless you ask.

## Running a floor on our questions

1. In the project: **New chat**.
2. Type a one-line request, then paste the **whole** `research/questions.md` below it, in one message. For example:
   > Floor 3: propose research strategies for each of our three questions below.
3. For floor 3, write your own choice in `research/strategy_guess.md` **before** you run it (the lecturer's
   order: you choose first). Then compare, decide who is right, and write the decision down.
4. Log the run (see "The test log" below).

If a question changes, it goes through floor 2 and floor 3 again.

## The test log

The lecturer asks for a log of every run (session 3, slide 55): the date and file versions, the request and the
answer, pass or fail, and what was fixed. For every run:
1. Add a row to `logs/test_log.md`.
2. Save the full request and answer in `logs/floorN/<date>_runN.md`, with our assessment.
3. If it failed: fix the rules or the decision table and run again. Never change the test case.

## Updating the research idea PDF

Edit `research/research_idea.html`, then print it to PDF (or open it in a browser and print → Save as PDF):

```bash
cd research && google-chrome --headless=new --no-pdf-header-footer --print-to-pdf=research_idea.pdf "file://$PWD/research_idea.html"
```

Keep it to two pages.

## Testing (acceptance tests)

Each floor is tested like software before it is trusted.

1. In the project: **New chat** (one chat per test).
2. Open `tests_to_paste/floorN/testNN.txt`, copy **all** its text, paste it into the chat and send.
   Paste the text — do not attach the file.
3. Compare the answer with the same test in `answers_keep_private/floorN_expected.md`
   and fill in the results table there.
4. Check every answer also for: floor name at the start, English, short and plain sentences, technical terms
   defined on first use, no flattery.
5. Run the important tests twice in new chats — Claude's answers vary between runs.

Floor 2 tests are also just pasted; the `question-checker` skill loads by itself. If the answer has no criteria
tables, the skill was not used: check that it is switched on, or start the message with "Use floor 2 —".

**If a test fails:** find the broken rule (its number is in the expected file), make it sharper, update it
(constitution → Instructions; skill → `SKILL.md`, rebuild the zip, upload again), and run the test again
in a new chat. Record what you changed.

## Changing a skill

Edit the skill's files (for example `floor2/question-checker/SKILL.md`, or `floor3/strategy-advisor/decision-table.md`),
then rebuild the zip. The folder inside the zip must keep the skill's exact name:

```bash
cd floor2 && rm -f question-checker.zip && zip -r question-checker.zip question-checker
cd floor3 && rm -f strategy-advisor.zip && zip -r strategy-advisor.zip strategy-advisor
```

Floor 3 order (from the lecture): write and fix the decision table first, then the skill. A failed floor 3 test is
fixed in the rules or in the decision table, never by changing the test case.

Upload the new zip in Claude (Customize → Skills), replacing the old version.

## Adding a floor

For every new floor:
1. `floorN/<skill-name>/SKILL.md` — the skill (YAML header with `name` and `description`, then rules,
   criteria and procedure). From floor 9 on, add `scripts/` with code for the steps that must be exact.
2. `floorN/<skill-name>.zip` — upload to Claude.
3. `floorN/requirements_floorN.md` — role, capabilities, boundaries, how it is tested → upload to Context.
4. `tests_to_paste/floorN/` and `answers_keep_private/floorN_expected.md` — the acceptance tests.

## AI-use record

Following the course rules, record for every version: the tool (Claude), plan (free), model, version and date,
and keep the prompts and answers of the test runs.
