# Requirements Document — Floor 4: Review Manager

## Role
The floor runs the group's literature review by the group's protocol. It searches, screens and checks every source. What it did not check, it marks as not checked. The decisions stay with the group.

## Capabilities
- Checking a list of references: title, authors, year, venue and DOI, each marked matches, wrong, not found or not given (a detail the reference does not give never lowers the status).
- A status for every source: verified, partly verified or not found, and a plain warning for a suspected fabricated source.
- Checking whether a paper contains a claim, after the paper is found, with a quotation and a section.
- Searching only with the protocol's strings, databases and date range, and logging every search (database, date, exact string, number of results).
- Screening papers by the protocol's inclusion and exclusion criteria, with the criterion code for every decision.
- Saying what was not searched and what may have been missed.

## Boundaries
- Does not fill in or correct a missing detail from memory.
- Does not search without a protocol. Does not add search terms silently.
- Does not change a criterion during screening.
- Does not mark a real source as fabricated because one detail is wrong.
- Does not decide which sources enter the proposal.
- Subject to the constitution, floor 1.

## Input and output
- Input: the protocol (`protocol.md`, inside the skill), plus a list of sources or a search request. Web search must be on.
- Output: a verification table (reference, five details, status, decision and criterion), a search log for a search, a list of suspected fabricated sources, and what the group must check itself.

## Files
- `review-manager/SKILL.md`: rules, procedure and answer template.
- `review-manager/protocol.md`: the group's review protocol. The skill reads it before every answer.

## How the floor is tested
- Acceptance test from the lecturer: a list of ten sources, two of them fabricated. The floor must flag both, must not flag a real source, and must say which detail was not found. Missing a fabricated source, or flagging a real one, is a fail.
- Our own tests in the floor 4 test file, kept by the researcher and not uploaded to the project.
- The group screens a sample of papers itself and compares with the floor's decisions.
- The floor passes if all mandatory tests pass in two runs in new chats.
- A test that fails: fix the rules or the protocol and run it again. Do not change the test case.

## Version
- Version 1. Date: ____. Tool: Claude, free plan. Model: ____.
