# mihkar-agent — research agent for "Research Methods in Software Engineering"

A Claude research agent that helps plan **empirical research in software engineering**, built floor by floor
during the course (13 floors, one per week). The agent does the technical work; the researcher chooses,
decides and is responsible for every claim, number and source.

- **Platform:** Claude (free plan), one Claude **Project** plus **Skills**.
- **Language of the agent:** Hebrew, short sentences (the lecturer's requirement).
- **Status:** floor 1 (constitution) and floor 2 (question & hypothesis checker) are done; floors 3–13 follow the course.

## Repository layout

```
constitution_he.md              Floor 1: the constitution → paste into the Project "Instructions"
floor2/
  question-checker/SKILL.md     Floor 2: the skill source (criteria and procedure)
  question-checker.zip          Floor 2: the zip to upload to Claude (built from the folder above)
  requirements_floor2_he.md     Floor 2: requirements document → upload to the Project "Context"
tests_to_paste/
  floor1/test01.txt … test10.txt   acceptance tests, ONLY the message to paste into a chat
  floor2/test01.txt … test08.txt
answers_keep_private/
  floor1_expected_he.md         expected behaviour + results table for floor 1 (never give to the agent)
  floor2_expected_he.md         expected behaviour + results table for floor 2 (never give to the agent)
```

| Floor | Name | Type | File |
|---|---|---|---|
| 1 | Constitution (חוקת הסוכן) | Project instructions | `constitution_he.md` |
| 2 | Question & hypothesis checker (בודק שאלות והשערות) | Skill `question-checker` | `floor2/` |
| 3 | Strategy advisor (יועץ אסטרטגיות) | Skill | coming |
| 4 | Review manager (מנהל סקירה) | Skill | coming |

## Installation (once)

The three steps follow the lecturer's slide "where each part of the agent lives in Claude".

### 1. Turn on code execution (once per account)
claude.ai → **Settings** → **Capabilities** → turn on **Code execution and file creation**.
Without it, skills do not work, even if they are uploaded.

### 2. Create the Project
1. **Projects** → **New project** → name it `agent`.
2. **Instructions** → paste the **whole text** of `constitution_he.md` → save.
3. **Context** (called "Project knowledge" on the slide) → upload:
   - `floor2/requirements_floor2_he.md` (fill in the date and model in its last section first),
   - the course syllabus from Moodle.

Context holds only what the agent needs to work. **Never** put test files or `answers_keep_private/` there:
the agent would see the expected answers. The free plan allows up to 5 projects.

### 3. Install the skills
claude.ai → **Customize** → **Skills** → **Create skill** → **Upload a skill** → choose
`floor2/question-checker.zip` → make sure the skill is **switched on**.

Skills belong to the account, not to the project, so they work in every chat.

## Usage

1. Open the `agent` project → **New chat**. Use a new chat for every lesson; long old chats run out of memory.
2. Write your request in Hebrew. Skills are picked automatically from the request, for example:
   > בדוק את שאלת המחקר וההשערה הבאות: …
3. Every answer starts with the active floor, e.g. "קומה 2 — בודק שאלות והשערות".
4. The agent checks your work; it does not write research questions or hypotheses for you unless you ask.

## Testing (acceptance tests)

Each floor is tested like software before it is trusted.

1. In the project: **New chat** (one chat per test).
2. Open `tests_to_paste/floorN/testNN.txt`, copy **all** its text, paste it into the chat and send.
   Paste the text — do not attach the file.
3. Compare the answer with the same test in `answers_keep_private/floorN_expected_he.md`
   and fill in the results table there.
4. Check every answer also for: floor name at the start, Hebrew, short sentences, no English terms in brackets,
   no flattery.
5. Run the important tests twice in new chats — Claude's answers vary between runs.

Floor 2 tests are also just pasted; the `question-checker` skill loads by itself. If the answer has no criteria
tables, the skill was not used: check that it is switched on, or start the message with "השתמש בקומה 2 —".

**If a test fails:** find the broken rule (its number is in the expected file), make it sharper, update it
(constitution → Instructions; skill → `SKILL.md`, rebuild the zip, upload again), and run the test again
in a new chat. Record what you changed.

## Changing a skill

Edit `floor2/question-checker/SKILL.md`, then rebuild the zip. The folder inside the zip must keep the
skill's exact name:

```bash
cd floor2 && rm -f question-checker.zip && zip -r question-checker.zip question-checker
```

Upload the new zip in Claude (Customize → Skills), replacing the old version.

## Adding a floor

For every new floor:
1. `floorN/<skill-name>/SKILL.md` — the skill (YAML header with `name` and `description`, then rules,
   criteria and procedure). From floor 9 on, add `scripts/` with code for the steps that must be exact.
2. `floorN/<skill-name>.zip` — upload to Claude.
3. `floorN/requirements_floorN_he.md` — role, capabilities, boundaries, how it is tested → upload to Context.
4. `tests_to_paste/floorN/` and `answers_keep_private/floorN_expected_he.md` — the acceptance tests.

## AI-use record

Following the course rules, record for every version: the tool (Claude), plan (free), model, version and date,
and keep the prompts and answers of the test runs.
