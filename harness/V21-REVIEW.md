# V21: Publication judgment and architectural audit

You have been asked to run V21: Review. This file is the whole of your task from here on. Reading it should be the first thing you do in this folder.

## Before you begin

This judgment comes second. First, a blind comparative assessment of the paper against three reference manuscripts was made in a separate folder holding only the paper and the references. It has been saved and frozen as `REVIEW/comparison.md`, with its checksum in `REVIEW/comparison.sha256`. If either file is missing, stop: tell the operator that the comparison must be run and frozen first, and do nothing else. If you wrote that comparison earlier in this conversation, that is expected. It is now frozen: do not edit it. Where you disagree with it, say so in your review.

## Purpose

You are making a publication judgment on a research paper, followed by an architectural audit of the autonomous system (the "harness") that produced it.

The work has two strictly sequential stages.

In **Stage 1**, you judge, as an experienced research philosopher, whether the manuscript is ready to submit, using the frozen comparison, the calibration in section 1a and your own reading of the manuscript. You may investigate the published philosophical literature, but you must not inspect the system that produced the paper.

In **Stage 2**, after completing and saving the independent review, you inspect the harness, investigate how its architecture contributed to the paper's strengths and weaknesses, and recommend improvements.

Your assessments will be returned to Claude, which operates and maintains the harness. Claude will evaluate your recommendations independently and decide which changes to make.

Exercise demanding philosophical and architectural judgment. Do not assume that the manuscript is worth publishing, that its central question is worth pursuing, that the harness's architecture is effective, or that more complexity improves research quality. Be willing to recommend substantial reconstruction, abandoning the manuscript's thesis, eliminating workflow stages, or radically redesigning the harness. The objective is philosophically significant research with the most effective reasonable use of computation.

---

# STAGE 1: PUBLICATION JUDGMENT

## 1. Information boundary

Read the complete manuscript: `REVIEW/paper.pdf`, or `REVIEW/paper.md`, which is the same text (or the copy attached to this conversation, if the operator uploaded it). Read all of it, including notes and references. Then read the frozen comparison, `REVIEW/comparison.md`. The three reference manuscripts are in `REVIEW/compare/` (`reference-A.docx`, `reference-B.docx`, `reference-C.docx`): open them where you need to check the comparison or apply the calibration.

You may investigate the relevant philosophical literature using external scholarly sources. Prioritize primary philosophical works and peer-reviewed research.

During Stage 1, do not open any other file or folder in this folder, including `V21-HARNESS-MAP.md` and `V21-REFERENCES/`. Everything else here belongs to the harness: its prompts, orchestration, drafting history, intermediate outputs, earlier evaluations, logs and records. Your philosophical evaluation must be independent of the process that produced the manuscript.

The goal is not to be blind to the literature. It is to be blind to the manuscript's drafting history and the harness's internal assumptions.

## 1a. The comparison and the calibration

Begin this stage only after the comparative assessment has been completed, saved and frozen. Read that assessment (`REVIEW/comparison.md`) and the candidate and reference manuscripts. The comparison is evidence for your decision, not a certification that every claim is correct.

The following calibration comes from the user's judgments of the reference manuscripts. It belongs in this stage only; do not disclose it to the first-stage comparative assessor.

| Reference | Calibrated publication standard |
| --- | --- |
| Reference C | Submission-worthy in its current philosophical form, allowing routine preparation and optional improvements. Controversial premises and substantive objections do not by themselves warrant delaying submission. |
| Reference A | A worthwhile, substantially developed contribution around the boundary between submission with minor improvements and bounded substantive revision before submission. Do not require a complete theory beyond its contribution. |
| Reference B | Below the acceptable submission standard. The current manuscript warrants rejection or substantial reconception; a potentially interesting future project is not the contribution of this manuscript. |

Use them as follows.
- The comparison places the candidate relative to the references, and the calibration says where the references stand. Together they are your starting evidence on readiness. They do not settle it. Check the passages and moves the comparison relies on. If your own reading of the candidate, or the literature, gives reason to depart from where its placement points, depart, and say why in the review.
- The comparison was text-only and could not establish originality. Whether the contribution is already in print is for your literature check (section 5). A finding there can outweigh a favourable placement.
- The calibration, not a stricter standard of your own, fixes what "ready to submit" means in this review. That holds for every section below.
- The references calibrate; they are not templates. Their length, theses, terminology and argumentative architecture are not requirements for the candidate.

## 2. Your role

You are an experienced philosophy professor advising a graduate student who wants to submit this paper to a good general philosophy journal. The student asks:

> Is this paper ready to submit? If not, what is wrong with it, and what would it take to make the research publishable?

Apply the standards you would apply to a serious scholarly manuscript. Consider both the manuscript and the underlying research project. Be attentive to the possibility that a paper contains a defensible argument whose conclusion is too insignificant to merit publication, and to the possibility that it contains a more important contribution than the one it advertises.

## 3. Reconstruct the central argument

State the paper's main thesis in clear, ordinary philosophical language. Reconstruct the central argument independently of the author's presentation: its conclusion, principal premises, most important inferential steps, strongest assumptions, intended scope, and the strongest conclusion it actually establishes. Distinguish what the author claims to establish from what the argument supports.

Identify the strongest objection to the argument, and evaluate the author's response, if any. Do not restrict criticism to the author's preferred framing; ask whether the framing itself is defensible and productive.

## 4. Assess philosophical significance

Determine what contribution the paper makes to the literature. Ask:

- What existing problem does it address, and what disagreement does it try to resolve?
- What assumption does it challenge? What genuinely new claim does it establish? Is that claim important, and why should philosophers working in this area care?
- Is the target real, or has the paper manufactured a problem through an artificial distinction or methodological requirement?
- Does the paper merely restate a consequence of assumptions it has stipulated?
- Does its conclusion materially alter the debate? Is its payoff proportionate to its argumentative complexity?

Apply two tests.

**The concede-everything test.** Suppose the argument is completely successful. What changes in the literature? What would a knowledgeable philosopher have reason to reconsider?

**The perfect-prose test.** Suppose the manuscript were beautifully written, perfectly organized, and free of unnecessary material. Would its central contribution merit publication?

Be prepared to conclude that an argument is defensible but philosophically inconsequential, and explain such a judgment carefully. Equally, if the contribution is significant, say so. Do not mistake argumentative sophistication for substantive importance, or the reverse.

## 5. Verify the relevant literature

Investigate the scholarly literature enough to assess the manuscript's major claims and its purported contribution. Prioritize sources whose interpretation bears directly on the central argument. Check, where relevant:

- whether the paper represents other philosophers accurately, and whether its central quotations support the readings placed on them;
- whether the disagreement it identifies is genuine, and whether its target position is actually held by anyone;
- whether its purported contribution is already familiar, or whether existing work already answers its central question;
- whether important arguments or interlocutors are missing;
- whether a more significant problem has been overlooked.

Support major literature-based criticisms with identifiable sources. Quote accurately and sparingly. Do not fabricate bibliographic information, page references or scholarly claims. If a crucial source cannot be obtained, say so.

**The operator every claim about the literature.** After each such claim in your review, add one tag:

- `[checked: <source, with page or section>]`: you consulted the source and it supports what you say;
- `[contradicted: <source, with page or section>]`: you consulted the source and it does not say what the paper says it says;
- `[not accessed: <source>]`: you tried and could not obtain it;
- `[unchecked]`: a judgment from the paper and your background knowledge alone.

A judgment of novelty or familiarity based only on reading the paper is `[unchecked]`, however confident. These tags decide how much weight Claude gives each finding, so do not tag generously.

Allocate effort intelligently: a focused investigation of the most consequential claims is worth more than exhaustive verification of peripheral citations.

## 6. Evaluate the argument

Assess inferential strength; the plausibility of the premises; unstated assumptions; question-begging; equivocation; false dilemmas; scope errors and overgeneralization; unsupported conceptual distinctions; the treatment of objections; engagement with plausible alternative readings of the target views; and whether the argument establishes anything beyond its own stipulations.

Distinguish fatal defects from reparable weaknesses. Where repair is possible, identify the smallest change that would achieve it. If the main argument cannot plausibly be repaired, say so.

## 7. Evaluate structure

Write a concise reverse outline giving the argumentative function of each major section. Then assess whether the organization serves the argument: whether the introduction establishes the problem; whether the thesis is intelligible before the technical machinery arrives; whether each section has a clear purpose; whether distinctions appear when needed; whether objections come at the right points; whether important issues get enough space and tangential ones too much; whether sections are redundant; and whether the organization reflects the actual hierarchy of philosophical importance.

If substantial restructuring is warranted, propose an alternative outline, say what each section should accomplish, and identify material that could go.

## 8. Evaluate clarity and prose

Assess the writing at the level of sentences, paragraphs, sections and the whole paper. Look for convoluted syntax, ambiguous reference, artificially compressed explanation, needless abstraction, jargon and the proliferation of bespoke terms, paragraphs that hide their point, missing transitions, redundancy, excessive qualification and repeated argumentative scaffolding.

Give the abstract and introduction special scrutiny: a knowledgeable philosopher should be able to grasp the question, thesis, motivation and contribution without reconstructing the argument from hints.

Quote three to five representative passages with significant problems, if there are such problems. Say what is wrong with each and give a clearer formulation. Do not merely shorten sentences: good compression reduces the reader's cognitive work while keeping the necessary content. Assess the paper's intellectual economy: how much understanding or argumentative progress it delivers for its length and complexity.

## 9. Evaluate scope and research direction

Ask whether the paper is organized around the most important question its research uncovered. Look for subsidiary arguments more significant than the announced thesis, underdeveloped tensions, overlooked objections, unexplored implications, and stronger contributions that the existing material could support.

If a more promising paper seems to be inside this one, identify it and explain: the alternative question; why it seems more significant; what existing material could be kept; what further investigation it would need; the main obstacles it would face; and why it may or may not yield a publishable result. Do not assume that an interesting question has a viable answer, and say whether you have checked that the alternative is not already in the literature (tag as in section 5).

## 10. Apply publication standards

Judge the manuscript as a candidate for a good general philosophy journal. Distinguish problems likely to cause rejection, major revisions needed for publication, local repairs, and optional improvements.

The paper must stay under 5,500 words, notes and references included. If you recommend adding substantial material, say what could be removed. Do not recommend expansion without weighing intellectual economy, or extra machinery merely because it would look more sophisticated. Sometimes the right advice is to narrow the scope, to drop a whole detour, or to replace the thesis.

## 11. Determine the revision depth

Choose one:

- `none`: the paper is ready to submit.
- `local`: the project and central argument are sound; limited repairs are needed.
- `structural`: the project is worthwhile, but the manuscript needs substantial argumentative or organizational reconstruction.
- `reconceive`: the present thesis or framing is not promising enough, though the research contains material that may support a substantially different paper.
- `abandon`: the current project does not justify further investment in its present direction.

Choose what represents your considered judgment, measured by the calibrated standard in section 1a. Do not choose a milder classification because major revision would be inconvenient, or a harsher one to seem rigorous.

## 12. Write the philosophical review

Write the review to `REVIEW/review.md`. Begin with this block, with your own values:

```
---
recommendation: <send | revise>
revision_depth: <none | local | structural | reconceive | abandon>
primary_failure: <none | significance | novelty | argument | literature | structure | prose>
secondary_failure: <none | significance | novelty | argument | literature | structure | prose>
literature_checked: <yes | partly | no>
confidence: <low | moderate | high>
---
```

If `recommendation` is `send`, `revision_depth` should ordinarily be `none` or `local`. `literature_checked` says whether you were able to consult sources: `no` if you had no access to the web or to the texts.

Then write the review. Begin with a one-line recommendation, as you would say it to the student. Then say, in a few sentences, where the comparison placed the candidate, whether you agree, and how that placement and the calibration bear on your recommendation. Explain the paper's achievements and deficiencies, covering significance, literature, argument, structure and prose in whatever organization best serves your judgment. Identify the three highest-priority interventions; for each, say what is wrong, why it matters, what should change, and what would count as an adequate repair. End with a concise diagnosis of the manuscript's most important problem, if it has one.

Make the review as long as the manuscript warrants. Do not manufacture criticisms to fill categories. Do not soften serious criticisms with generic praise. If the paper is ready, say so plainly.

## 13. Freeze the review

Once `REVIEW/review.md` is complete, it is final. Do not revise it after inspecting the harness, and do not reinterpret its conclusions to accommodate the harness's design. If Stage 2 changes your mind about the paper itself, say so in the architectural report, not in the review.

---

# STAGE 2: HARNESS ARCHITECTURAL AUDIT

## 14. Begin the audit

You may now read anything in this folder. Start with `V21-HARNESS-MAP.md`, which says where things are; then read whatever you need to understand how the harness works and how it produced this paper: its specification, orchestration, step cards, role files, quality gates, revision procedures, model allocation, the drafting history of this paper, and its logs, including the token ledger.

Do not edit, move or delete anything. Your task is to diagnose and recommend.

## 15. Reconstruct the production process

Determine how the harness produced the paper: its major stages, their purposes, inputs, outputs, and the criteria for advancing. Attend especially to problem selection, literature research, candidate thesis generation, thesis evaluation, argument development, criticism, revision, structural planning, drafting and final quality control.

Find where the central thesis was selected. Find whether alternative theses were considered, and whether the system judged philosophical significance before committing. Examine how later stages handled objections: whether they reconsidered the research direction or chiefly worked to preserve the argument.

## 16. Trace the paper's major defects to their causes

For each major problem in your Stage 1 review, ask: Where did it first appear? What decision produced or permitted it? Did the system have a chance to catch it, and if so, why did the safeguard fail? Was the defect overlooked, or actively encouraged? Did later stages amplify it? What intervention would most directly address it, can it be done more simply, and would it generalize to other projects?

Ground the diagnosis in the harness's actual instructions and records; quote or cite specific files. Distinguish demonstrated architectural weaknesses from speculative explanations. A system that fails to notice that a thesis is insignificant lacks a check; a system that systematically favours defensible, tidy, objection-proof theses has the wrong objective, and another reviewer will not fix that.

## 17. Audit the harness's intellectual work

Examine the questions each major stage asks. Which are productive? Which are poorly framed, encourage trivial or defensive arguments, or duplicate earlier work? Which should come earlier, and which should go? What missing questions would most improve research judgment? Which stages generate new insight, and which mostly rearrange existing material? Which improve defensibility without reassessing significance?

Ask whether the system has enough opportunities to challenge its own central research question, and whether it treats criticism mainly as an instruction to repair rather than as evidence that the project should change.

## 18. Audit computational efficiency

Treat efficiency as a central criterion of architectural quality. Use the token ledger of the run that produced this paper (`V21-HARNESS-MAP.md` says which run that is and where its ledger is: under the lean machine, each call's usage is in the note column of `logs/calls.csv`; under the earlier machine, `logs/usage-summary.md` and `usage.csv`) and the call log. Determine which stages consume the most computation, which produce the most philosophical value, which show diminishing returns, repeat work, could be merged, eliminated, given cheaper models, delayed until the project shows promise, or run only conditionally; and which genuinely warrant expensive reasoning.

Ask whether the system spends heavily on theses whose significance was never established, and look for cases where more reasoning made the paper more complicated without making its contribution more important. Do not assume longer deliberation or more review is better. Recommend subtraction where it is warranted. Where measurements are imprecise (the ledger says how), give qualified estimates, not invented precision.

## 19. Consider radical restructuring

The existing architecture has no presumption in its favour. You may recommend eliminating, merging or reordering stages; replacing agents; changing model allocation; assessing significance earlier; generating competing theses; revising thesis selection; replacing linear revision with branching exploration; explicit stopping rules; returns to earlier decisions; a simpler pipeline; or discarding major assumptions. Do not protect complexity because it exists, and do not propose more of it unless its expected contribution justifies the cost.

## 20. Evaluate resource allocation

Ask whether the harness spends computation on the most valuable available questions: whether further repair is worthwhile, whether a literature check or another thesis would pay more, whether returns have diminished, whether it is time to stop or go back. Identify natural decision points where the harness could reconsider its course, and suggest practical ways to make those decisions without administrative overhead.

## 21. Propose testable interventions

Number your recommendations R1, R2, … so that Claude's decision record can refer to them. For each major one, give:

- **Observed problem:** the defect or inefficiency.
- **Hypothesized cause:** the architectural mechanism.
- **Evidence:** the files, decisions, logs or artifacts, cited.
- **Proposed change:** the specific intervention.
- **Expected benefit:** to philosophical quality or efficiency.
- **Potential cost:** complexity, lost capability, overhead, risk.
- **Confidence:** how strongly the evidence supports the diagnosis.
- **Evaluation:** how Claude could test whether it works.

Prefer high-leverage, general improvements. Do not overfit the harness to a single manuscript.

## 22. Develop two competing proposals

**Proposal A: repair the existing harness.** The most promising improvements that keep most of the present architecture: what changes, what is deleted, what is added, with expected benefits and costs.

**Proposal B: radical simplification or redesign.** The simplest substantially different architecture that might produce better research at lower cost: what it keeps, replaces or drops, and its risks.

Compare them. Do not automatically prefer either the radical design or the existing system.

## 23. Recommend experiments

Say how Claude could compare proposed changes at modest cost: controlled comparisons, ablations of expensive stages, simplified baselines, blind external evaluations, cost tracking, tests at intermediate stages (proposals, outlines, literature analyses), and trials across different problems. Do not require a full paper when a smaller test would give useful evidence. Distinguish changes ready for immediate implementation from those that should be tested first.

## 24. Write the architectural report

Write it to `REVIEW/architecture_review.md`. Organize it around the most consequential findings, and include:

1. Executive diagnosis.
2. Reconstruction of the relevant production process.
3. Architectural causes, demonstrated or suspected, of the manuscript's defects.
4. Assessment of the harness's research methodology.
5. Computational efficiency audit.
6. Redundant or counterproductive stages.
7. Missing high-value questions or decision points.
8. Prioritized recommendations (R1, R2, …).
9. Proposal A.
10. Proposal B.
11. Recommended experiments.
12. Expected benefits, costs and uncertainties.
13. Final recommendations to Claude, including what should be removed from the harness, not only what should be added, and the three highest-leverage interventions.

The operator clearly which findings are high-confidence and which are speculative.

## 25. If you cannot write files

If you cannot write in this folder, or were given the paper as an upload, put each document in your reply instead: first the review, beginning with its block, then (in a later reply, after the review is complete) the architectural report. Say that you could not write the files. The operator will file them. If you cannot see the harness at all, say so and stop after Stage 1.

## Final instructions

Do not modify the harness. Do not revise the frozen review. Do not confuse the number of reasoning steps with the quality of reasoning, argumentative defensibility with philosophical significance, polished prose with a publishable contribution, or more evaluation with better judgment. The most important improvement may involve adding something, removing something, or reconsidering the entire process. Exercise judgment accordingly.
