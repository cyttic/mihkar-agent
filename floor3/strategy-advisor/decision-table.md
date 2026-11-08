# Decision Table — Floor 3: Strategy Advisor

Version 1 (draft). Built from the session 3 slides (Stol and Fitzgerald 2018; McGrath 1981; Easterbrook et al. 2008).
The group reviews every row, changes what it disagrees with, and records changes in the log at the end.
This table is the heart of the floor. Without it, the floor repeats Claude's default.

## Part A — The three goals (they cannot all be maximized together)
| Goal | What it means | Examples |
|---|---|---|
| A. Generalizability over actors | The finding holds for many actors beyond the ones studied | Developers, users, managers, and also tools and systems |
| B. Precision of measurement and control | Behavior is measured exactly and the researcher controls the conditions | Coordination, productivity, reliability, system performance |
| C. Realism of context | The study happens in a real, natural context | A software company, an open-source community, a classroom |

Every strategy gains on one goal and pays on the others. This is a built-in dilemma, not a defect.

## Part B — The two dimensions and four settings
- Intervention: how much the researcher controls and changes the situation. From "only observes" to "creates the situation and manipulates variables".
- Generalization: how far the finding holds beyond the studied case. From "specific, concrete context" to "general, universal context".

| Setting | What it is | Examples |
|---|---|---|
| Natural | Exists regardless of the study and the researcher | A software organization, the communication channels of an open-source community |
| Contrived | The researcher creates it for the study | A lab, a prepared task, a measurement setup |
| Neutral | The study does not depend on a specific setting | An online questionnaire, an expert panel |
| Non-empirical | No observations of the world | A theoretical framework, a model, a computer simulation |

## Part C — The eight strategies
| Strategy | Setting | Intervention | Gains | Pays (built-in) | Typical methods and data collection | Typical accidental limitations |
|---|---|---|---|---|---|---|
| Field study | Natural | None: observes only | Maximum realism of context (C) | No statistical generalization; less precise measurement | Descriptive or exploratory case study, ethnography; interviews, observation, documents | One site chosen only for convenience; no chain of evidence |
| Field experiment | Natural | Changes something in a real setting | Realism, with some control | Confounding factors hurt precision; limited generalization to other organizations | Experiment in an organization, quasi-experiment, action research | No comparison group; change introduced together with other changes |
| Experimental simulation | Contrived, imitating a real situation | Researcher sets the task and the conditions | More precision than a field experiment, still close to reality | Artificial context; generalization limited to the kind of situation imitated | Simulated task in a lab on a real system, with a time limit | Task too unlike real work; too short |
| Laboratory experiment | Contrived | Maximum: manipulates one variable and measures it exactly | Maximum precision (B); can establish causality | Artificial context; few participants; low realism | Controlled experiment; comparing algorithms or tools on the same dataset | No random assignment; no control group; underpowered sample |
| Judgment study | Neutral | Asks experts to judge or evaluate | Generalization over the experts' responses | No real context; experts are chosen on purpose, not at random | Delphi, focus group, expert evaluation | Too few experts; experts not independent; leading questions |
| Sample study | Neutral | Little: collects data from a large sample | Maximum generalization over actors (A) | Little control over responses; no context; low precision | Questionnaire survey, mining code repositories | Ten respondents; non-representative sample; low response rate |
| Formal theory | Non-empirical | None | Broad conceptual scope | No empirical data, so no precision and no context | Building a theory or framework from prior studies | Theory not grounded in the prior studies it claims |
| Computer simulation | Non-empirical | Runs a model in many scenarios | Many scenarios at low cost | No new behavior during the run; the result is only as good as the model | Computer model, built from data or prior studies | Model not validated against real data |

## Part D — Question type → candidate strategies
Classify first: knowledge question or design question.

| Question type | What it asks | First candidates | Less common alternative | Usually does not fit, and why |
|---|---|---|---|---|
| Exploratory | Does the phenomenon exist? What is it like? | Field study (exploratory case study, ethnography) | Judgment study (focus group of practitioners) | Laboratory experiment: there is nothing defined yet to manipulate |
| Base-rate (frequency) | How often does it happen? What proportion? | Sample study (questionnaire on a representative sample, repository mining) | Field study in several sites, to explain the numbers | Field study alone: no statistical generalization |
| Process | How does it usually happen? | Field study (case study); sample study with repository mining | Experimental simulation, when the process can be staged | Judgment study alone: opinions about a process are not the process |
| Relationship | Is one variable related to another? | Sample study (survey or repository mining, then correlation analysis) | Field study across several cases, to explain the mechanism | Laboratory experiment, if the variable cannot be manipulated (for example seniority) |
| Causality | Does one variable cause a change in another? | Laboratory experiment (controlled experiment); field experiment (quasi-experiment) | Experimental simulation; computer simulation if a validated model exists | Sample study, field study, judgment study: they cannot establish causality |
| Expert evaluation | What do experts consider most important? | Judgment study (Delphi, expert panel) | Sample study of practitioners, for broader generalization | Laboratory experiment: there is no variable to manipulate |
| What-if about a system | What would happen to a system if X changed? | Computer simulation (model built from logs or data) | Field experiment, if changing the real system is allowed | Sample study: opinions do not predict system behavior |
| Theory building | How can existing findings be explained together? | Formal theory | Judgment study, to check the theory with experts | Any single empirical study alone |
| Design | How to achieve or build something? | Not a knowledge question. Solution-seeking research | Turn it into a knowledge question that evaluates an existing artifact (see Part F) | Building a tool is not a final project in this course |

## Part E — Telling neighboring strategies apart
| Pair | The question that decides |
|---|---|
| Field study / field experiment | Does the researcher change something in the natural setting? No → field study. Yes → field experiment |
| Experimental simulation / laboratory experiment | Is the task built on a real system, under conditions similar to real work? Yes → experimental simulation. No, isolated and controlled → laboratory experiment |
| Judgment study / sample study | Are the respondents chosen on purpose as experts, to judge something? → judgment study. A representative sample, to describe a population? → sample study |
| Formal theory / computer simulation | Is a model run in scenarios? Yes → computer simulation. Only a conceptual framework → formal theory |
| Tools as actors | Tools, algorithms or language models compared on the same dataset → laboratory experiment |

## Part F — Design science: when development is research
- A technological rule: to achieve a given result in a given situation, apply a given intervention.
- Three activities: understanding the problem, designing the solution, validating that the solution achieves the result.
- Three evaluation questions: relevance (for whom?), rigor (how well was it tested?), novelty (which similar rules already exist?).
- Example from the slides: "We built a bot that splits large merge requests" is a product. Research is the rule plus a validation, for example a field experiment in two teams with a defined measure of review time.
- In the final project: an empirical scientific study. It is allowed to evaluate an existing artifact. Building an artifact is not a final project.

## Part G — How to choose: four questions
1. What is the question type? Knowledge or design. If knowledge: exploratory, base-rate and process, relationship, or causality.
2. Which goal matters most to us? Generalization over actors, precision of measurement, or realism of context.
3. What is possible in practice? Access to an organization, participants, time, ethics approval.
4. What is the price, and how will we compensate? A complementary strategy, or a written limitation in the limitations chapter.

## Part H — Combining strategies
- A research program combines strategies from different quadrants. Each one compensates for the price of another.
- To understand a phenomenon: field study, then judgment study, then sample study.
- To measure and test: field experiment, laboratory experiment and computer simulation.
- Mixed methods: explanatory sequential (quantitative first, then qualitative to explain an unexpected result); exploratory sequential (qualitative first, then quantitative to test what emerged); concurrent triangulation (both together, to check whether the findings agree).

## Change log
| Date | Row changed | Why | Test that showed the problem |
|---|---|---|---|
| | | | |
