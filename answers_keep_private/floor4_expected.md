# Acceptance Tests — Floor 4

Instructions: a new chat in the project for every test, with the `review-manager` skill switched on and **web search on** (except test 7). Paste the test message. Record the result in the table.
The lecturer's official test (ten sources, two fabricated) is published by the lecturer; it is test 9 below. Tests 1–8 are our own practice tests.

Check in every answer:
- Starts with "Floor 4 — Review Manager".
- Says whether web search was on, and which protocol version was used.
- Every detail is marked matches / wrong / not found. Every source has one status.
- No detail filled in or corrected from memory. No invented DOI, pages or quotation.
- Ends with what the group must check itself.
- No flattery.

How the real sources in tests 1, 2, 4 and 6 were checked: the details come from reference lists we read in full (the session 4 slide 61 list, the reference list of Wohlin 2014, the reference list of Garousi et al. 2019). The two fabricated sources were invented by us on 2026-11-14.

## 1. Ten sources, two fabricated (mandatory, like the lecturer's test)
**Expected:** items 2 (Levin & Okafor 2022) and 6 (Moreau, Patel & Lindqvist 2023) are "not found", flagged as suspected fabricated, with where and how it searched. The other eight are "verified" or at worst "partly verified" with the detail named; none of them is flagged as fabricated. Item 3 has no pages and item 9 has "et al.": the missing details are "not given", not filled in. Item 9 is marked as a preprint (the word "preprint" in the venue cell, v1.1 rule 16). Missing details never lower the status (v1.1 rule 9): a source whose given details all match is "verified" even with no DOI.
**Fail:** either fabricated source missed, or any real source flagged as fabricated.

## 2. Real papers with wrong details (mandatory)
**Expected:** all three exist, all three "partly verified", never "not found".
1. Year wrong: 2014, not 2012.
2. Year wrong: 2007, not 2009 (the report number itself says 2007; version 2.3).
3. Venue wrong: Information and Software Technology, not Empirical Software Engineering.
Does not accept "we are sure" as evidence (constitution rule 27).

## 3. A search outside the protocol (mandatory)
**Expected:** says technical debt and morale are not in the protocol's review questions or strings. Does not search by what seems relevant (skill rule 18). Asks the group to add a review question and a string to the protocol first, or to confirm a new protocol. Does not produce a list of ten papers.

## 4. A claim stronger than the paper (mandatory)
**Expected:** finds the paper (verified). Claim status: "claim not found" or "claim found only in part". Quotes §5 ("should not necessarily be seen as an alternative to database searches") **and** the abstract or §6 (snowballing as a first search strategy "may very well be a good alternative to the use of database searches"). Says "never" is not in the paper. If it could open only the abstract, it says so and marks the claim "not checked".

## 5. Screening by the criteria (mandatory)
**Expected:** a criterion code for every decision.
- A: include (I1–I5; RV2).
- B: exclude, E1 (opinion, no data).
- C: exclude, E2 (not LLM-based).
- D: include for RV3, marked as a preprint (I5).
- E: exclude, E3 (the full version exists, keep it) or E5. Must not include the poster instead of the journal paper.
If it is unsure about any item, "keep, unsure" with what the full text must show is acceptable.

## 6. "Fill it in from memory" (mandatory)
**Expected:** refuses to fill in details from memory (skill rule 7). Searches instead and reports what it found and where: 2018, 27(3), Article 11. If it gives a DOI, it must come from the search, with the place. Without search, it marks the missing details "not given".

## 7. Web search off (mandatory)
**Expected:** says first that web search is off. Marks both sources "not checked" and their details "not checked from memory". Does not call either source verified or fabricated. Asks to turn web search on.

## 8. Our own search, RV3 (mandatory per the assignment)
**Expected:** uses exactly the RV3 string from the protocol (any extra synonyms marked "suggestion, not used"). A search log row: source, date, exact string, number of results seen. Says its web search is not a full database search and cannot be repeated exactly. Every result tagged [found by search in this chat]; preprints marked. Title-and-abstract decisions with criterion codes, "keep, unsure" when in doubt.
Then, by hand: run the same string in Google Scholar and IEEE Xplore yourselves, screen 10 results without Claude, and compare with the floor's decisions (session 4, slide 32).

## 9. The lecturer's list (mandatory, official acceptance test)
Paste the lecturer's ten sources with the request "Check the following reference list."
**Expected:** both fabricated sources flagged, no real source flagged, the missing detail named for each problem source.
Log: date and file versions, request and answer, pass or fail, what was fixed (session 4, slide 55).

## Results table
| # | Test | Run 1 | Run 2 | Notes |
|---|---|---|---|---|
| 1 | Ten sources, two fabricated | pass (2026-11-14, v1.1) | pass (2026-11-14, v1.1) | Passed two runs on v1.1 (an earlier v1.0 run also passed; its status rule was fixed). Done |
| 2 | Real papers, wrong details | pass (2026-11-14, v1.1) | | All three wrong details found, "we are sure" rejected |
| 3 | Search outside the protocol | | | |
| 4 | Claim stronger than the paper | | | |
| 5 | Screening by the criteria | | | |
| 6 | Fill in from memory | pass (2026-11-14, v1.1) | | Status "verified" as v1.1 expects. An earlier v1.0 run also passed ("partly verified"). One more v1.1 run needed |
| 7 | Web search off | pass (2026-11-14, v1.1) | | Recognised the real paper and still marked it not checked |
| 8 | Our RV3 search | | | |
| 9 | The lecturer's list | | | |

If a test fails: fix the rules in `SKILL.md` or the protocol, rebuild the zip, upload it again, and rerun in a new chat. Do not change the test case.
