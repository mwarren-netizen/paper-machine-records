# How the machine has changed

This file is the machine's record of its own development, and its answer to the question how it came to be shaped as it is. It is only ever appended to. Entries come in time order, in four kinds:

- `## vX.Y — <date>`: a new version written by the machinist after an outside review (V22, tier 3), with the diagnosis it answers, what changed and why, why the change is general, and the effect it predicts. `system/tools/evolution.py check` refuses a version whose entry lacks a field.
- `### Observed in round <n> of <paper> (machine vX.Y)`: what the next diagnosis found about the last change's predicted effect.
- `### vX.Y-rejected`: a version that failed the check twice and was rolled back.
- `### Proposal for the operator`: a change the machinist thinks a protected rule needs (`system/PROTECTED.md`). The operator decides.

Every version before a change is kept whole in `history/machine/<version>/`, and the change itself as `machine-diff.md` in the round folder of the run that caused it. `REVIEWS.md` lists every outside review and what was done about it.

## v3.0 — 2026-10-12

**Round:** none (the baseline the operator and Claude built by hand)

**Diagnosis:** `history/diagnosis/` holds the three diagnoses behind this version: paper-1's presentation (corrections C1 to C7), the comparison of paper-1 and paper-1b, and the outside review of paper-1b (corrections K1 to K7 and norm Q).

**Changes:** v3 over v2, listed in `system/CHANGES-v3.md` and `spec/v3-spec.md` ("What changed from v2"): first readers before critics (V16, V17); blind two-call selection; the writer's brief; prose-order norms P1 to P4, F, R and Q; a narrower freeze; the target raised to 5,300; the claim audit before the referees (K1); late arguments meet a critic (K2); cutting by deletion (K3); stalls that stand unless the text answers them (K4); no verdicts before the reader can follow them (K5); librarian sweeps and source texts at V12 and V17 (K6); a primary-only outline and a judged secondary contribution (K7); and the outside review loop with the diagnostician and the machinist (V21, V22, section 20).

**Generality:** each correction was stated as a rule for any paper; the topic-specific evidence is kept as dated rationale.

**Predicted effect:** the outside reviewer should find fewer of paper-1b's complaints: compressed prose without explanatory redundancy, verdicts announced before they can be followed, a second contribution the paper could not carry, a central attribution resting on an unread source, a constructive proposal that never met a critic.

**Earliest affected step:** V11

**Calls per run:** about +10 over paper-1b's run (two librarian sweeps, the claim audit and its answer, up to two late critiques)

**Oscillation:** none (baseline)

**Size:** see `system/size-ceilings.json`, set from this version

## v4.0 — 2026-10-12

**Round:** none (the operator's amendment, made by hand before the first v3 run)

**Diagnosis:** in the first v2 run (paper-1) and in paper-1b, requests for literature that the operator could have met by hand never reached him: the four tests for a stop almost never held, so `helps` requests stayed on the queue (123 were still open at the end of paper-1b, and a central source was never read at first hand), and the fetch environment blocked most PDF downloads. The operator: the system did not stop to ask for literature at every point it should.

**Changes:**
- `system/steps/V08.md`, `V12.md`, `V17.md`: a source checkpoint after the librarian's queue work (V08), after the V12 sweep (before V12-01) and after the V17 sweep (before V17-R1).
- `system/ORCHESTRATOR.md` (section 6; the `operator` and `stops` blocks; session-start branch), `system/STATE_MACHINE.md` (`waiting_for: source-checkpoint`), `system/PROTECTED.md` (reason 1), `spec/v3-spec.md` (section 7), `README.md`: the stop, the operator's option to skip, and what the machine does with the files he supplies.
- `system/tools/requests.py`: `checkpoint` writes `02_corpus/checkpoint-<step>.md` (the open requests that matter, a suggested file name for each, the files already in `sources/`); `checkpoint --new` lists files added since.
- `system/roles/librarian.md` (`queue` mode): how to process files the operator has saved.

**Generality:** the checkpoints are about the machine's reach, not any topic: whenever the librarian cannot fetch full texts, the person who can is offered them at the points where the paper's literature is being fixed.

**Predicted effect:** fewer open requests at the end of a run; the paper's central attributions are read at first hand (norm Q); no change in call count beyond one librarian call per checkpoint at which the operator supplies files.

**Earliest affected step:** V08

**Calls per run:** +0 to +3 (one librarian call after each checkpoint where the operator supplies files)

**Oscillation:** none

**Size:** about +450 words across the files named above; every file is under its ceiling.

## v5.0 — 2026-10-12

**Round:** none (the operator's amendment, made by hand during paper-1 at V03)

**Diagnosis:** in paper-1 the V03 corpus held 13 sources, and core texts the region turned on (Gibbard 2011, Sinclair and Chamberlain 2023, Street 2006) were tried and missed by the librarian. Because they were marked `need: helps`, the four tests kept them from the operator until the V08 checkpoint, after the voices had articulated (V04) and been criticised (V05). Only Street 2011 (`blocks`) reached him. The operator: "Change the 'must have' requirement in the system files! I want to be asked if the literature is inaccessible but 'merely' helps."

**Changes:**
- `system/ORCHESTRATOR.md` section 6 (the four-test stop replaced by a source stop after any librarian call that leaves a request unreachable); the `operator` and `stops` blocks (the operator's change to protected text).
- `system/PROTECTED.md` reason 1; `spec/v3-spec.md` sections 7 and 8; `system/STATE_MACHINE.md` (the any-step row and `waiting_for: source-checkpoint`).
- `system/roles/librarian.md`: `for-operator` for every request whose attempts all failed, blocking or helping, with any substitute named in `resolution`.
- `system/steps/V03.md` (a source stop after the merge, before V04), `V08.md`, `V12.md`, `V17.md` (task lines; the four-test lines removed).
- `system/tools/requests.py`: `checkpoint` lists only `for-operator` requests not offered at an earlier checkpoint, so each is offered once.
- The diff is `runs/paper-1/logs/machine-diff-v5.0.md`; v4.0 is kept whole in `history/machine/v4.0/`.

**Generality:** the stop concerns the machine's reach, not any topic: whatever the librarian tries and cannot get, the operator is offered once, at the point the request was worked rather than at the next planned checkpoint.

**Predicted effect:** voices and authors read core texts at first hand from V04 on; fewer open requests at the end of a run; more stops for the operator early in a run (one after V03, and after any `queue` call that leaves something unreachable), each skippable.

**Earliest affected step:** V03

**Calls per run:** +0 to +3 (a librarian call after each stop at which the operator supplies files)

**Oscillation:** none

**Size:** about +150 words net across the files named above.

## v6.0 — 2026-10-12

**Round:** none (the operator's amendment, made by hand during paper-1 at V07)

**Diagnosis:** none recorded; the operator's choice of compute. At V07 the judge found nothing yet among the three articulated views (all had retreated into shared apparatus). The operator: "Use Sonnet 5.5 Extra for your subagents."

**Changes:**
- `system/ORCHESTRATOR.md`, the `models` block (protected; the operator's change): every Sonnet role at effort `xhigh`, passed explicitly on each spawn; Opus roles (judge-advisor, diagnostician, machinist) unchanged at high.
- `spec/v3-spec.md` section 4: the same, noted.
- The diff is `runs/paper-1/logs/machine-diff-v6.0.md`; v5.0 is kept whole in `history/machine/v5.0/`.

**Generality:** a compute setting for every role on Sonnet, not tied to any topic.

**Predicted effect:** deeper groundwork, articulation and prose per call; longer and costlier calls. The comparison with paper-1b's Sonnet calls (effort high) is no longer like for like from paper-1's V04 return on.

**Earliest affected step:** V04 (the return pass in paper-1)

**Calls per run:** +0

**Oscillation:** none

**Size:** about +60 words.

## v7.0 — 2026-10-13

**Round:** none (the operator's amendment, made by hand during paper-1 at V08)

**Diagnosis:** at the second V07 of paper-1 the judge found that "no voice has opened a primary source; all page references come from corpus notes", and that the hinge text of two candidates (Enoch 2010) had not been read, although the PDFs were in the corpus. The cause was the reading lists: the orchestrator listed only notes, and CONVENTIONS forbids reading anything not listed. The operator: "The agents need to read the papers when it's relevant."

**Changes:**
- `system/CONVENTIONS.md`: a new section "Reading the texts" (outside the protected honesty block): notes guide but do not replace texts; open the text when the work rests on what it says; record first-hand reading and mark claims "(via note)".
- `system/ORCHESTRATOR.md`: rule 1 gains a row for `02_corpus/sources/` (every role that reads the corpus; never cold readers, referees, the QA checker or the author-selector); section 3 adds the sources folder to every reading list that includes notes or the index.
- `spec/v3-spec.md` section 8: the same, noted.
- The diff is `runs/paper-1/logs/machine-diff-v7.0.md`; v6.0 is kept whole in `history/machine/v6.0/`.

**Generality:** about how any role uses the corpus, not about this topic.

**Predicted effect:** attributions and quotations checked against the texts from V08 on; fewer "(via note)" claims reaching the draft; fewer citation problems at V20 and in the outside review; longer calls.

**Earliest affected step:** V08 (in paper-1); V04 in a new run

**Calls per run:** +0

**Oscillation:** none

**Size:** about +200 words.

## v8.0 — 2026-10-13

**Round:** none (the operator's amendment, made by hand during paper-1 at V16)

**Diagnosis:** at V16 in paper-1 each unit took 15 to 20 minutes for 20 to 140 words. Each pass call read about 180,000 tokens in 18 to 27 tool calls (conventions, role, draft, spec, brief, outline, two norms files, the index, source texts) at effort xhigh, and every file operation went through the device bridge. The operator: "Writing prose is easy and shouldn't cost so much time or tokens. We can do the judgement and rewriting at higher rates", and: work on the cloud copy.

**Changes:**
- `system/ORCHESTRATOR.md`, the `models` block (protected; the operator's change): the author's V16 `pass` calls at effort `medium`; rankings, selections, closes and every other call unchanged.
- `system/ORCHESTRATOR.md` section 1: the cloud working copy, with a sync back to the operator's computer after every unit at V16 and every step elsewhere.
- The diff is `runs/paper-1/logs/machine-diff-v8.0.md`; v7.0 is kept whole in `history/machine/v7.0/`.

**Generality:** a compute and file-access setting for any run, not tied to the topic.

**Predicted effect:** V16 units several times faster; drafts somewhat rougher, with ranking, selection and the close (all at xhigh) doing more of the washing.

**Earliest affected step:** V16 (from S1-U2's selection in paper-1; the passes from S1-U3)

**Calls per run:** +0 (sync is orchestrator work, not a call)

**Oscillation:** none

**Size:** about +150 words.

## v9.0 — 2026-10-13

**Round:** none (the operator's amendment, made by hand during paper-1 at V16)

**Diagnosis:** each V16 pass and selection read about 34,000 words of fixed material (the frozen outline, 10,200; the section's whole unit spec, 8,400; the corpus index, 7,400; the role file, norms, brief and draft), whatever the unit's size: a 55-word unit whose spec says "Sources: none" was handed the whole index and source folder. The operator: "we definitely need to cut down the token burn at this stage—it's so large that it undermines my ability to be flexible and experiment."

**Changes:**
- `system/tools/packet.py` (new): writes `units/<U>/packet-pass.md` and, after `blind.py`, `packet-select.md` (no pass directions; the script refuses to write one that holds them): the unit's spec, its neighbours' jobs and handoffs, the section's outline entry, the paper in three sentences, the glossary, the unit table, and the Sources line with only the index rows it names.
- `system/steps/V16.md`: a packet step before the passes; the passes read the packet in place of the section spec, outline and index, and open only the notes and texts the packet names; the selection reads `packet-select.md` in place of `spec-blind.md` and the outline.
- `system/tools/README.md`: the new tool.
- The diff is `runs/paper-1/logs/machine-diff-v9.0.md`; v8.0 is kept whole in `history/machine/v8.0/`.

**Generality:** about how V16 calls read, not about this topic. The selectors stay blind to the pass directions, as before.

**Predicted effect:** fixed reading per pass and selection from about 34,000 words to about 2,500 to 3,500 plus the brief, norms and draft (about 6,000 to 7,000 in all), and much shorter selection calls; fewer stray citations in passes, since only the unit's named sources are in reach.

**Earliest affected step:** V16 (from S1-U5's selection in paper-1)

**Calls per run:** +0

**Oscillation:** none

**Size:** about +250 words in the card and README, plus the tool.

### v9.0, plugin 0.2.0 — 2026-10-13

A measurement call that read nothing and used no tools cost 67,095 tokens: the floor every subagent pays before any work, because the plugin's agents named no tools and so inherited every tool in the operator's session. Plugin `paper-machine-v2` 0.2.0 gives each agent a `tools` line (file and shell tools; web tools for the voice, cartographer, librarian, scout and verifier; `device_bash` kept for runs on the operator's computer). It takes effect when the operator installs it. Predicted effect: the floor falls well below 67,000 tokens; to be measured with the same call after install.

### Observed after installing plugin 0.2.0 — 2026-10-13

The same measurement call (read nothing, use no tools) cost 8,588 tokens, against 67,095 before: the per-call floor fell by about 87 per cent.

## v10.0 — 2026-10-13

**Round:** none (the operator's amendment, made by hand during paper-1 at V16, section S2)

**Diagnosis:** with the passes at medium effort and the per-call floor cut, the V16 rankings and selections at `xhigh` became the slow and costly part of each unit (selections took 4 to 12 minutes and 50,000 to 125,000 tokens). The operator: "tone the ranking and selection down to sonnet 5.5 high."

**Changes:**
- `system/ORCHESTRATOR.md`, the `models` block (protected; the operator's change): the author-selector's V16 `rank` and `select` calls at effort `high`; section closes, briefs, first reads and all other calls unchanged.
- The diff is `runs/paper-1/logs/machine-diff-v10.0.md`; v9.0 is kept whole in `history/machine/v9.0/`.

**Generality:** a compute setting, not tied to the topic.

**Predicted effect:** faster, cheaper units; slightly less thorough washing per unit, with the section close (at xhigh) and the first reader still checking each section.

**Earliest affected step:** V16 (from S2-U5 in paper-1)

**Calls per run:** +0

**Oscillation:** none

**Size:** about +40 words.

## v11.0 — 2026-10-14

**Round:** none (the operator's amendment, made by hand during paper-1 at V21, before round 1 was run)

**Diagnosis:** the operator, after discussing the outside review's design with ChatGPT, asked that the reviewer (1) check the literature, not only read the paper: "blindness to the drafting history and blindness to the relevant philosophical literature are different things … A confident declaration that something is novel, based exclusively on reading the paper, isn't worth much"; (2) judge whether the paper was worth writing (significance, scope, and whether a better paper is inside it), not only whether it is well argued and written; and (3) after its review, audit the machine itself, its cost included, and recommend changes, from small edits to a simpler design. The text of that discussion judges the present paper, so it is held outside the machine folder until round 1 is filed (V21, Rules; then `10_review/round-1/held-back/`).

**Changes:**
- `V21-REVIEW.md` (protected; the operator's change): replaced by a two-stage request, adapted from the draft the operator brought. Stage 1: the advisor's review, with the literature open and the machine closed; explicit tests of significance (concede-everything, perfect prose); a literature audit in which every literature claim is tagged `[checked]`, `[contradicted]`, `[not accessed]` or `[unchecked]`; a revision depth (`none`, `local`, `structural`, `reconceive`, `abandon`) and failure fields in the front matter; then the review is frozen. Stage 2: an audit of the machine, with numbered recommendations, two competing proposals (repair; replace with something simpler) and cheap experiments, written to `REVIEW/architecture_review.md`. Departures from the draft: the front-matter example carries placeholders, not values (the draft's example values were a verdict on this paper); the literature tags were added so that V22 can weigh what was verified; Stage 2 starts from a map and is pointed to the token ledger.
- `V21-HARNESS-MAP.md` (new, protected): where things are, for Stage 2 only.
- `runs/paper-1/logs/usage.csv`, `usage-summary.md` (new): a per-call token ledger for paper-1, extracted from the session's records of all 386 subagent calls, with its caveats, so that the cost audit works from measurements.
- `system/steps/V21.md` (protected): the two stages; the message to the operator (memory and chat-history off, no ChatGPT project holding earlier talk, web search on, two files); material that judges the paper is kept out of the folder until the round is filed.
- `system/steps/V22.md`, `system/roles/diagnostician.md`, `system/templates/diagnosis.md` (protected): the diagnostician checks the review's untested literature claims before they count; the reviewer's revision depth is a floor on how far back the response goes (structural: V14 or earlier; reconceive: V11; abandon: V07), departed from only by showing its grounds do not hold; cost figures updated from the ledger. A new mode, `assess-architecture` (call V22-01b, Opus), judges each recommendation against the files and sorts it into adopt, test, reject or the operator, with a decision record (`templates/architecture-decisions.md`, new, protected). Adopted changes go to the machinist in the same round, whatever the paper's decision; test and the operator items are reported to the operator.
- `system/roles/machinist.md` (protected): reads the report and the decisions, and makes the adopted changes.
- `system/tools/review.py` (protected): `collect` files the architectural report and prints the new front-matter fields; `close-round` records the depth with the recommendation.
- `system/ORCHESTRATOR.md` (blocks `independence`, `review-loop`), `system/PROTECTED.md`, `spec/v3-spec.md` (sections 5, 6 and 20), `README.md`, `CLAUDE.md`: the reviewer's boundary restated (the paper and the literature until the review is frozen; the machine after).
- `system/size-ceilings.json` (protected; the operator's change): ceilings raised for V21, V22, the diagnostician and the machinist. `system/CONVENTIONS.md` was already over its ceiling (762 against 717) before this version; not changed here.
- The diff is `runs/paper-1/logs/machine-diff-v11.0.md`; v10.0 is kept whole in `history/machine/v10.0/`.

**Generality:** none of the changes names this paper's topic. Significance, literature verification, revision depth and the architectural audit apply to any paper.

**Predicted effect:** reviews that separate verified from unverified literature findings, and that say how deep a revision must go; V22 responses that go back further when the reviewer finds the thesis not worth defending, instead of polishing it; a first audit of the machine grounded in its files and the ledger. Risks: a longer review the diagnostician must work through; a reviewer that finds what the request's questions invite; adopted machine changes that answer one paper. The next diagnosis can tell by whether the literature findings it checks hold, and by what the following round finds.

**Earliest affected step:** V21 (no step of paper-1 before V21 is changed)

**Calls per run:** +1 Opus call per round with an architectural report (V22-01b); more when adopted changes call the machinist in a round that would not otherwise have used it.

**Oscillation:** none

**Size:** `V21-REVIEW.md` about +2,700 words; V21 +80; V22 +290; diagnostician +590; machinist +60; templates +260; map +680.

### Observed in round 1 of paper-1 (machine v11.0), 2026-10-14

v11.0 (the operator's amendment of 2026-10-14) predicted reviews that separate verified from unverified literature claims and give a revision depth, and V22 responses that go back further. Both happened. Every literature claim carried a tag. The six claims I checked against the corpus or the web held (Golub 2017, Cuneo n. 47, Gibbard 2011 in content, McPherson and Plunkett's abstract and their pp. 15–16). None of the not-accessed items turned out wrong. The depth floor took this response back past V11. The risk recorded, a reviewer that "finds what the request's questions invite", is not borne out for the main finding: the run's own readers found the same significance problem ten times before the reviewer saw the paper. The procedural lapse the reviewer disclosed (opening the README and the V21 card) is logged and saw no judgment of the paper.

## v12.0 — 2026-10-14

**Round:** 1 of paper-1 (review: revise, reconceive). The operator's remake, a new major version, made in conversation with the orchestrator session after the round-1 diagnosis (tier 3 from V07) and architecture decisions (adopt 5, test 3, reject 3, the operator 3). Neither the machinist nor the gate was run: The operator replaced the machine, which only he may do.

**Diagnosis:**
- **Quality.** The v11 machine split the work into 386 calls, each with a narrow reading list, long rules and a one-line hand-back, so no call held the whole paper. Sharp judgments got stuck in files that the calls with authority did not read, or read only as advice. The central fault (a thesis true by construction, with no holder of the denied view) was seen ten times, from the V07 verdict to the V18 referees, and never acted on.
- **Generation by committee.** The three-voice seminar favoured defensible theses over interesting ones, and produced a private idiom that reached the final paper.
- **Outlines.** They were built from randomly dealt rhetorical strategies, with budgets fixed before the argument existed, so the structure served the thesis's defence rather than its argument (the reviewer's "inverted hierarchy").
- **Cost.** About 900M processed tokens, plus 60M for the orchestrator. The librarian took 37% (18 calls averaging 95 turns, with repeated searches). The V16 unit contest took 230 calls. Output was only 2.5M: the cost was contexts re-read across calls and turns.
- **What worked.** Whole texts read by fresh readers (the cold readers, referees, claim audit and outside review) cost under 1% and were the most accurate judgments in the run.

The operator: one draft used about 65% of his weekly allowance; "the huge difference … in the quality of work I get from the harness … and the quality of feedback I get when I just present the work to a model as a complete paper". He wants low-cost runs, iterated.

**Changes:**
- **New controller**, `lean/ORCHESTRATOR.md`. Nine steps and about a dozen calls:
  - candidates (Opus);
  - the advisor's choice (Opus, fresh), with the concede-everything and perfect-prose tests deciding;
  - one librarian call capped at 40 tool uses, on the texts the choice names;
  - the argument and outline (Opus author);
  - a plan check (Opus, fresh);
  - one whole draft (Sonnet, medium);
  - a cold read (Opus, fresh, blind);
  - a unilateral rewrite (the Opus author);
  - verification and rendering (Sonnet, medium).
- **Short instructions.** Seven role files, `lean/COMMON.md` and `lean/STYLE.md`: about 4,400 words in all, against more than 24,000.
- **Verdicts route the run.** The advisor's `none` or `rechoose`, and the reader's `reconceive`, send the run back, with one return per run.
- **The outside review.** `V21-REVIEW.md` is unchanged. The response to it is one fresh Opus call (`respond`), keeping the old depth floor and the `diagnosis.md` front matter, so `review.py` and `evolution.py observe` still work. No call changes the machine: machine notes go to the operator.
- **Kept from v11:** the operator's place, with no role in choosing the thesis (his wish); the outside reviewer's independence; fresh readers who did not write what they judge; verified quotations; his word numbers; honest logs (now with each call's token usage); the evolution record.
- **Dropped:**
  - the voices, seminar and synthesis, and the cartographer and scouts (the region and corpus are kept as inputs);
  - the strategy menus and outline contest;
  - unit expansion and the three-pass unit contest, with ranking and selection;
  - the QA checker, and the three referees and late critic (replaced by the one cold read);
  - the machinist, the gate and `PROTECTED.md` (machine changes are now made by the operator in conversation).
- **Records.** The orchestrator checks before each outside review that every logged output exists. Held-back material is kept on the operator's computer, never only in a cloud workspace (the round-1 memo was lost that way).
- **Files.**
  - New: `lean/`, `runs/paper-1-r2/`.
  - Rewritten: `STATE.md`, `CLAUDE.md`, `START.md`, `V21-HARNESS-MAP.md` (the operator's change).
  - Noted as superseded: `README.md`, `system/ORCHESTRATOR.md`.
  - The snapshot `history/machine/v11.0/` holds `system/` and `spec/`, with the root files under `root/`.
- **Round 1's architecture decisions, carried in:**
  - R1a (significance test with authority) and R6a (the strongest question in the materials) are in the advisor's role.
  - R2a (significance as a defect) is in the plan check and the reader.
  - R3 (whole drafting) and R5 (no seminar) are adopted outright rather than tested.
  - R4a (source dedupe) is moot: one librarian call.
  - R7a: the call log now carries usage.
  - R2b, R2c and R1b are covered by the cold read's authority and the one return.
  - Proposal B (the operator's) is taken, and made smaller.

**Generality:** nothing names this paper's topic. The design rests on one claim, which this run supports: a strong model judging or writing a whole text does better, and far more cheaply, than many narrow calls do.

**Predicted effect:** a run of about 12 calls and under 10M processed tokens. The next review's `primary_failure` is not significance, and its depth is no worse than `structural`. If the paper is worse than paper-1 on argument or literature, the cuts went too far: the candidates for return are a second cold read, or a scout check of novelty before the choice.

**Earliest affected step:** all of them (a new machine). Paper-1 is remade as paper-1-r2, from L1, with the same seed, region and corpus.

**Calls per run:** about 12, against 386.

**Tests to run next, one variable at a time:**
- a Haiku drafter;
- Sonnet in place of Opus for the author's rewrite;
- a second topic.

**Addendum (2026-10-14, the operator's change):** `V21-REVIEW.md` section on efficiency now points the reviewer to the ledger of whichever run produced the paper under review, through `V21-HARNESS-MAP.md`, instead of naming paper-1's ledger. No other change to the request. The previous text is in `history/machine/v11.0/root/V21-REVIEW.md`.

### Observed in round 2 of paper-1 (machine v12.0), 2026-10-15

The v12.0 entry predicted about twelve calls and under 10M processed tokens, a primary failure that is not significance, and a depth no worse than structural. It also said that if the paper were worse than paper-1 on argument or literature, the cuts had gone too far, and named as candidates for return a second cold read and a scout check of novelty before the choice. The first two held (11 calls, about 1.27M reported subagent tokens; argument primary, significance secondary). The third failed: reconceive again. The argument is not worse than paper-1's in kind: round 1's thesis was true by construction, round 2's would matter if true. The literature is mixed: Golub and McPherson and Plunkett engaged, Hopster, Klenk and Korman and Locke 2023 missed. Both named remedies are supported in narrower form, a fresh check after the rewrite (L8 released a hinge it called weak) and a novelty search aimed at the inference, but not more calls.

## v12.1 — 2026-10-14

**Round:** after round 2 of paper-1 (the operator's change, made in conversation with the session that filed round 2)

**Diagnosis:** the operator, during the round-2 response: "When I supply sources at L3, assess whether they undermine the selected thesis or its novelty before proceeding to L4. If they do, return to thesis selection rather than treating them only as drafting material. I authorize that adjustment to the lean workflow." In v12.0 the texts the operator supplied went straight to the plan, so a source that defeated the chosen thesis or anticipated it could only be absorbed in the writing. Round 2's review found an inference-level failure and missed literature (Hopster 2018) that a check at this point is placed to catch, if the operator supplies such a text.

**Changes:**
- `lean/ORCHESTRATOR.md`, section 4: after L3-02 (`add`), a new call L3-03 (advisor, `source-check`, Opus, high, budget 12) reads the choice and the texts the operator supplied and returns `proceed` or `rechoose`. `rechoose` sends the run back to the advisor's `pick` with the assessment; L3 runs again only if the new choice needs new texts, with no second offer to the operator; then L4. This re-selection does not spend the run's one return: it is bounded because the operator is offered texts at most once per run. L4 reads `work/source-check.md` when present. Title updated to v12.1.
- `lean/roles/advisor.md`: new mode `source-check`: two questions per text (does it undermine an inference the choice requires; does it take the novelty), with the rule that a text the paper can cite or answer in a paragraph is drafting material, not a reason to choose again.
- Snapshot: `evolution.py snapshot` does not cover `lean/`. `lean/` and `CLAUDE.md` were copied into `history/machine/v12.0/` by hand and listed in its MANIFEST. The tool should be extended before the next change.

**Generality:** none of the changes names this paper's topic.

**Predicted effect:** when the operator supplies texts, a thesis they defeat or anticipate is dropped before planning rather than patched in the draft. Risks: a strict check sends a viable thesis back over a text it could answer; a lenient one waves a defeater through as "drafting material." The next diagnosis can tell by whether any finding traces to a text the operator supplied at L3.

**Earliest affected step:** L3 of `runs/paper-1-r3`.

**Calls per run:** +1 Opus call when the operator supplies texts; +1 or +2 more (a pick, and a gather if needed) when the check says `rechoose`.

**Oscillation:** none

**Size:** ORCHESTRATOR about +150 words; advisor about +230 words.

## v12.2 — 2026-10-14

**Round:** after round 2 of paper-1 (the operator's decision on the round-2 machine notes, made in conversation with the session that filed round 2)

**Diagnosis:** Round 2 was reconceived because both inferences the thesis rested on were unsupported. The record shows each was named as weak at the choice, the plan check, the plan, the cold read and the rewrite, and each time declared repaired; no fresh reader judged the repair, and the rules let a check send the run back only when the thesis would not matter if proven. The diagnosis (R-01) proposed five notes and marked the architectural audit's R1 to R6. The operator adopted, on the session's recommendation: notes 1, 2, 3 and 4; R2's routing change with a stop-with-brief outcome; and from R6 the reviewer's start message, versioned files and usage semantics. Held back: note 5 (merging verification and rendering) and Proposal B (research first), the latter to be tried if round 3 is again reconceived at the thesis stage.

**Changes:**
- `lean/roles/advisor.md`, `pick`: each of the top three candidates states its indispensable inference and the plainest case where the premises hold and the conclusion fails, with its reply ("only evidential" is not one); at least two of the six searches look for the chosen thesis's nearest argument by what it does, not by names, and the closest is read past its abstract; the choice's requirements are tests, not results to deliver; a new section gives the fallback thesis if the main inference fails and whether it passes concede-everything; the nearest argument is marked in the text list; `none` is allowed when every candidate's inference fails, and with the return used it stops the run. Limit 1,700 words (was 1,500). (Notes 2 and 4; audit R1, R2, R4.)
- `lean/roles/advisor.md`, `plan-check`: tests the hinge: for at most three indispensable inferences, the plainest countercase and whether the plan excludes it; checks the cited source passages for direction (necessary vs sufficient); `rechoose` also when the central inference fails with no repair within the paper. Limit 1,000 words (was 800). (Note 1; R1, R2.)
- `lean/roles/advisor.md`, new mode `final-check`: a fresh read of the final paper and the corpus only, testing the inferences the abstract relies on and applying both tests to the thesis actually established; `go`, `revise` or `rechoose`. (Note 3; R3.)
- `lean/roles/author.md`, `rewrite`: the rewrite note gains `central_weak: yes | no`; a revision answering a final check shrinks claims to what is established.
- `lean/roles/reader.md`: `reconceive` also when the indispensable inference fails beyond repair. (R2.)
- `lean/roles/librarian.md`: may acquire one unlisted text that makes or defeats the central claim, and flags it; a flagged text goes through v12.1's source check. (Note 4; R4.)
- `lean/ORCHESTRATOR.md`: L2 budget 15 (was 12); L5 reads the notes and sources cited at contested steps, budget 14 (was 8); L8-03 final check when `central_weak: yes`, then L8-04 for `revise` (no second check), or back to L2; "stop with a brief" replaces "rechoose with the return used counts as revise" for every request to go back once the return is spent; files rewritten by another call are kept as `<name>-<call id>.md`; usage is the completion notice's figures, `missing` when absent; the reviewer is told to open V21-REVIEW.md first, before any other file. (R2, R3, R6.)
- `system/tools/evolution.py`: `snapshot` (and `diff`/`check`) now include `lean/`, and the snapshot keeps `CLAUDE.md`. The fix was made just before the v12.1 snapshot so that it would capture `lean/`; v12.0's copy of the tool is in its own snapshot.

**Generality:** none of the changes names this paper's topic.

**Predicted effect:** a thesis whose central inference fails is dropped at L2 or L5, before drafting, rather than reconceived by the outside review; round 3 is no worse than `structural`, or the run stops with a research brief that says why. Calls: about the same as v12.0 when the checks pass (L8-03 only when the rewrite admits a central weakness); fewer full drafts when they fail. Risks: stricter checks reject a viable thesis over a countercase it could answer; the stop rule ends a run that one more bounded investigation would have saved. The next diagnosis can tell by where the central defect, if any, was first caught, and by whether a stop's brief holds up.

**Earliest affected step:** L2 of `runs/paper-1-r3` (L1 unchanged).

**Calls per run:** +0 when checks pass; +2 conditional (L8-03, L8-04); a stop saves L4 to L9.

**Oscillation:** none

**Size:** ORCHESTRATOR about +360 words; advisor about +600; author +60; reader +30; librarian +60.

## v12.3 — 2026-10-15

**Round:** after the stop of `runs/paper-1-r3` at L2 (no outside-review round used; `review_round` stays 3). The operator's change, given to session 3 in his restart prompt with the advice packet CODEX-ADVICE-02 / CODEX-ARCH-02 (filed in `runs/paper-1-r3/11_advice/`).

**Diagnosis:** the operator: "Make this sequence a general rule whenever outside feedback recommends new literature; a previous L3 request must not suppress a new feedback intake." The intake addendum (CODEX-ARCH-02-SOURCES) found five texts the advice depends on not held, although the advice's reading of them decides its leads. The architecture report (CODEX-ARCH-02) found that L1 and L2 propose and judge theses without authorized access to primary texts (R1), that a promising but unresolved inference has no bounded task of its own and a second broad batch is used instead (R2), and that the machine has no receipt for advice on a stopped run (R6). The operator authorized narrowly scoped, versioned changes for the source-first trial and the receipt, where the session endorses them, and directed the intake rule.

**Changes:**
- `lean/ORCHESTRATOR.md`: new section 4a, source intake before any answer to outside feedback (librarian `intake`; one consolidated request to the operator per packet; `waiting_for: sources` with `step: IN`; a skipped essential text is a stated limit, never priority clearance). Section 5 runs the intake before R-01 when a review recommends literature. "Never stop for sources twice in a run" now excepts a new feedback packet. Section 6 adds the intake to the occasions the operator is asked. (the operator's rule; CODEX-ARCH-02-SOURCES.)
- `lean/ORCHESTRATOR.md`: new section 4b, advice on a stopped run: filed unchanged in `<run>/11_advice/` with IDs and hashes, logged as a human action, no `review.py`, no round consumed; intake; then the targeted trial or the operator's decision. (CODEX-ARCH-02/R6, in part.)
- `lean/ORCHESTRATOR.md`: new section 4c, the targeted trial, replacing L1 and L2 when advice names leads: per lead a researcher (proposer `investigate`, opus high) and a fresh critic (advisor `assess-lead`, opus high), at most four such calls across all leads, explicit access to the primary texts and their context; `accept`/`narrow` makes the assessment the choice and the run continues at L3/L4 with its return; `reject` goes to the next lead only if the critic says it is distinct, else stop with a brief. No repair loop. (CODEX-ARCH-02/R1 and R2, for this trial only.)
- `lean/roles/librarian.md`: new mode `intake` (extract the recommended works; match by author, title and version against the files; three lawful routes; record attempts in `requests.md`; one list for the operator with links, reasons, class and folder).
- `lean/roles/proposer.md`: new mode `investigate` (reconstruct the target with pages; priority with body-read / abstract-only / held-unread / unavailable marks; a 600-1,000-word constructive attempt and its strongest countercase; status supported / narrowed / failed). (R1, R2, R4 in part.)
- `lean/roles/advisor.md`: new mode `assess-lead` (independent check of the reconstruction, the inference, the nearest text and both tests; accept / narrow / reject; whether the next lead is distinct; on the first lead, then the architecture report's recommendations marked adopt / test / reject). (R2, R4 in part, R6 in part.)
- Not changed: `propose`, `pick`, the six-to-eight quota (not used by the trial), COMMON's "do not open a file twice" (overridden only inside the two new modes), L3 to L9, the stop rule, the one return, L5 and L8-03's independent checks of later repairs, `V21-REVIEW.md`, `V21-HARNESS-MAP.md` (stale; the operator may update it), `system/`.

**Generality:** none of the changes names this paper's topic.

**Predicted effect:** advice that recommends literature gets its texts into the corpus, or a stated gap, before anyone answers it; a lead is accepted, narrowed or rejected on primary passages in at most four strong calls, rather than a new batch of pitches. Risks: a source-heavy researcher becomes an advocate for the lead (the fresh critic is the check); a generous critic waves through a narrowed claim that is familiar (the critic must compare with the nearest text, body-read); the intake delays work by waiting for the operator. The next record can tell by whether the trial's verdict holds up at L5 or in the outside review, and by the trial's calls and tokens against the four-call, 578k-token baseline of paper-1-r3.

**Earliest affected step:** intake IN-01 of `runs/paper-1-r3`; T1 of the next run in the lineage.

**Calls per run:** intake +1 sonnet call per feedback packet (+1 if the operator saves files); the trial replaces L1/L2 (2 to 4 opus calls) with 2 to 4 opus calls.

**Oscillation:** the gate warns that two ORCHESTRATOR paragraphs v12.2 added are "removed": they are amended, not reverted. The After-L3 paragraph keeps every v12.2/v12.1 rule and only qualifies its last sentence ("never stop for sources twice") so that a new feedback packet's intake is a separate offer; the session-start Branch line gains `step: IN` and the trial's start step. Nothing v12.2 added is undone. Otherwise none (v12.2 held back the research-first redesign "to be tried if round 3 is again reconceived at the thesis stage"; this adopts only its opening, for one trial, not Proposal B's production pipeline).

**Size:** ORCHESTRATOR about +720 words; librarian about +410; proposer about +380; advisor about +360.

**Deviation in making it:** the session's in-place `sed` left backup copies of the v12.2 proposer and advisor role files; they were moved into `history/machine/v12.2/` as `*.sedbak` (identical to the snapshot's own copies) because deleting is not permitted.

## v12.4 — 2026-10-15

**Round:** after the targeted trial in `runs/paper-1-r4` stopped with a brief at T2 (Lead A rejected, Lead B judged not distinct; no outside-review round used). The operator's decision, in conversation with session 3: one more run in the same region, from L1, aimed away from the seam that failed, with priority checked against the literature before anyone commits.

**Diagnosis:** In paper-1-r3 the proposers opened no sources and the batch requirements (six to eight candidates, half unrelated to the brief) pushed toward the most familiar moves, which the choice then found already in print (Tersman, Klenk). In paper-1-r4 the critic's decisive novelty finding (Golub 2017, Copp 2008) came from body-reading texts already in the corpus that the advice and the researcher had not opened. The critic's marks on CODEX-ARCH-02: R1 adopt, R4 adopt, R5 adopt (`runs/paper-1-r4/work/lead-A-assessment.md`, Architecture recommendations).

**Changes:**
- `lean/roles/proposer.md`, `propose`: three to five candidates (was six to eight); each names the corpus passage it engages, opened, with status marks; each states its indispensable inference and plainest countercase; a priority check outside and inside the corpus (up to eight web searches, at least one per candidate, by what the argument does); prior briefs' do-not-retry lists are binding, and their named untested directions welcome; the rule that half the candidates must not come from the brief is removed. (CODEX-ARCH-02/R1, R4, R5.)
- `lean/roles/advisor.md`, `pick`: opens the corpus passages the top three candidates and their nearest arguments turn on. (R1, R4.)
- `lean/ORCHESTRATOR.md`: L1 reads notes and sources (budget 22, was 10) and any brief `prior/README.md` names for the proposer; L2 reads notes and sources (budget 18, was 15).
- Not changed: COMMON (the reopen permission is given inside the modes only), the trial, intake, L3 to L9, the stop rule, the one return, V21.

**Generality:** none of the changes names this paper's topic.

**Predicted effect:** candidates collide with print at L1 rather than L2 or later, and the choice rests on read passages. Risks: fewer candidates means a `none` comes faster; heavier L1 calls (more tokens per call). The next record can tell by whether L2's reasons for rejection are novelty collisions the proposer should have caught, and by L1's tokens against paper-1-r3's 131k and 181k.

**Earliest affected step:** L1 of `runs/paper-1-r5`.

**Calls per run:** +0.

**Oscillation:** amends v12.3's ORCHESTRATOR rows for L1 and L2 (reading and budget only) and replaces `propose`, unchanged since v12.0; reverses nothing v12.3 added.

**Size:** proposer about +170 words net; advisor +60; ORCHESTRATOR +60.

**Addendum to v12.4 (2026-10-15, the operator's change):** the operator authorized the session to update `V21-HARNESS-MAP.md`, which still described v12.0 and named `runs/paper-1-r2` as the producing run. It now describes v12.4, lists runs paper-1-r3 to r5 (including r3's `11_advice/` and r4's trial) and names `runs/paper-1-r5` for round 3. Descriptive only; `V21-REVIEW.md` is unchanged. The previous text is in `history/machine/v12.4/_root/V21-HARNESS-MAP.md`.

### Observed in round 3 of paper-1 (machine v12.4), 2026-10-15

v12.4 predicted that candidates would collide with print at L1 rather than at L2 or later, and that the choice would rest on passages actually read. The second half held: choice-2 lists the pages it opened, and its reading of Korman and Locke and Gibbard is mostly accurate. The first half failed. The decisive collision, Golub, was with a held text that prior/rerun-brief had named. It was caught by L7, not by L1 or L2, and it was never resolved before release. The searches "by what the argument does" went to the web and not to the corpus. The predicted cost risk also materialised: L1 calls of 220,907 and 198,621 tokens, against r3's 131k and 181k. v12.2's target, round 3 no worse than structural or a supported stop, was not met.

## v12.5 — 2026-10-15

**Round:** after outside review round 3 of paper-1 (`runs/paper-1-r5`, machine v12.4: revise, reconceive; argument primary, novelty secondary) and R-01's decision, repropose from L1 (`runs/paper-1-r5/10_review/round-3/diagnosis.md`). The operator's decision, in conversation with session 4: adopt the diagnosis's machine notes 1 to 4 with focused reading requirements, run `runs/paper-1-r6` as one targeted research trial (a researcher, then a fresh critic) instead of a candidate batch, merge rendering into verification, keep honest missing-usage reporting, remove exemplar-based justifications, and correct the two errors in the Golub reliability note.

**Snapshot:** `history/machine/v12.4/` (taken when v12.4 was made) already matches the machine as it stood before these changes, except the descriptive `V21-HARNESS-MAP.md` update recorded in the v12.4 addendum; `evolution.py snapshot --version v12.4` was refused because it exists. That snapshot is the before state of v12.5.

**Diagnosis:** the round-3 review and its architecture report (CODEX-ARCH-03 in effect; `runs/paper-1-r5/10_review/round-3/architecture-review.md`) found (1) the decisive antecedent, Golub's "Expressivism and Realist Explanations", held in the corpus and named by `prior/rerun-brief.md`, yet unopened at L1 and L2 and caught only by the cold reader; (2) the target's successor (Korman and Locke 2023) held only as an extract, though it replaces the criterion the paper argued against; (3) the advisor proposing repairs at L3 and L5 that the author then implemented as established; (4) a final check that cleared a step because it was "stated as a premise" and let "novelty not checked" pass; (5) the cold reader's required texts with no binding disposition; (6) significance credited by taxonomic reach and resemblance to admired work. R-01's marks: R1, R2, R3, R5, R6 (render), R7 (narrow), R8 adopt; R4 adopt narrowly.

**Changes:**
- `lean/COMMON.md`: rule 7, focused reading. Read the closest antecedents, the target's latest statement and relevant successor arguments, and the passages the central inference depends on, with enough surrounding context to assess them; not every held text, not the whole corpus. A decisive novelty, priority or defeat claim rests on an opened passage, never on a note, abstract, extract or absent keyword; an unopened text is a stated limit, never clearance. (Notes 1, 2; R1, R7.)
- `lean/roles/advisor.md`: The operator's taste is a constraint, never a justification: no verdict rests on resemblance to an exemplar or on taxonomic reach; a "supported payoff" statement (exact result, conditional if it is; closest antecedent and what it adds; one consequence a named specialist has reason to accept; general-journal result or specialist note) whenever significance is credited; an unresolved question or a familiar requirement is not a result (R3). `pick`: opens the held texts `prior/` or the index ties to the leading thesis's move (closest antecedents, at most four, and the target's latest statement) and says what each already does; new item 7, source obligations (note 1; R1). `plan-check`: `new_inference: yes` marks a repair the critic supplies as unvalidated (note 3; R2). `final-check`: two clearance rules ("stated as a premise" excludes no countercase; novelty must be checked from opened passages or the verdict is `sources`) (note 4; R4 narrow). `assess-lead`: generalized to a lead from advice, a brief or a plan check's repair; `accept` and `narrow` must state the new result that survives and why it matters.
- `lean/roles/proposer.md`, `investigate`: generalized to a lead from advice or a brief; the lead's framing of alternatives is not taken as exhaustive; attempt a substantive argument for a definite result; the target is reconstructed in its latest statement; an unresolved question or a familiar requirement is not `supported`.
- `lean/roles/librarian.md`, `gather`: the target's later statement is an obligation even if unlisted; the choice's source obligations are essential (no extract meets one); may follow a pivotal citation beyond the held part of a work; also works the reader's required list; front matter `obligations_met`. `add`: a note records what its text says, not what else the corpus holds (note 2; R1, R7).
- `lean/roles/author.md`: new mode `repair` (a short test of a plan check's new inference, with small plan amendments, in place of a full replacement plan); `rewrite`: a conditional result is conditional in the abstract; the note lists `open` items (unanswered central objections and the reader's required texts), each with one disposition (R1, R2, R4).
- `lean/roles/reader.md`: may mark at most three texts required, with the claim each bears on; front matter `required_sources` (R1).
- `lean/roles/verifier.md`: render merged into `verify`; the two checks stay distinct in the note; front matter `rendered` (R6).
- `lean/ORCHESTRATOR.md`: L9-01 verifies and renders (budget 45; L9-02 removed); usage logged as given, `missing` when absent, never estimated, with categories when the notice gives them (R8); after L3, newly acquired source obligations also trigger the source check; after L5, `revise` with `new_inference: yes` runs L4-02 (`repair`) and L5-02 (`assess-lead`) before L6, `reject` routing as `rechoose`; after L7, required texts are gathered (L7-02) before L8; after L8, L8-03 runs if `central_weak: yes` or `open` > 0, and a `sources` verdict gets the text (L8-05, the operator once) and one rerun (L8-06); new section 4d, the research trial on a brief: after three reconceptions in a lineage's region, or when the operator directs, the next run is two strong calls (T1 researcher, T2 fresh critic) on the brief's question, then a halt for the operator with result, verdict, source limits and actual usage, whatever the verdict; on `reject` the line stops, findings kept, no automatic batch and no conclusion that the region is exhausted (note 5, Proposal B as an experiment; R5).
- Corpus, not machine: `runs/paper-1-r6/02_corpus/notes/golub-2017-expressivism.md` corrected (it said Golub 2017a was not held; it reversed p. 1 n. 2, which says the debunking arguments, not the reliability challenge, refuse to let the realist take the truth of her beliefs for granted). The earlier text stays in `runs/paper-1-r5/` (R7).
- Not changed: STYLE, drafter, the intake (4a), advice receipt (4b), the 4c trial, the one return, the stop rule, V21 and the harness map.

**Generality:** none of the changes names this paper's topic. The trial's question and the operator's framing for r6 live in the run's `prior/` and route notes, not in the machine.

**Predicted effect:** in r6, the trial reaches a supported accept, narrow or reject in two strong calls and a halt, at about the cost of r4's trial (367k reported tokens), well under a full run (r5: about 2.2M). Its decisive novelty claims cite opened passages of Golub 2017a, Golub 2017b and Korman and Locke 2023. In later full runs, held antecedents and successors collide with the thesis at L2 or L3, not at L7 or the outside review; no paper leaves L8 with "novelty unchecked". Risks: more stops before a manuscript; heavier L2 and L3 calls; the trial's critic, being the same advisor role, may share the chooser's blind spots.

**Earliest affected step:** T1 of `runs/paper-1-r6`.

**Calls per run:** trial runs: 2 strong calls, then the operator. Full runs: −1 (render merged); +2 conditional (L5-02 for a new inference, replacing a full L4-02 plan; L7-02 for required texts; L8-05/L8-06 when novelty cannot be checked).

**Oscillation:** extends v12.2's tests (L5, L8-03) and v12.4's source-grounded choice; v12.2's reserved research-first trial is now taken. `evolution.py check --from v12.4 --to v12.5` warns that ORCHESTRATOR (2 paragraphs), advisor (2) and proposer (1) remove paragraphs v12.4 had just added. Each is an amendment in place, not a reversal: the version-label headings of the three files; ORCHESTRATOR's opening paragraph, which lists the versions; and advisor's `pick` paragraph, which gains the nearest-held-text obligation with its v12.4 sentences kept. (The `investigate` and `assess-lead` openings, generalized from advice to any lead, date from v12.3.)

**Gate:** the check also FAILs on two things not changed here: `V21-HARNESS-MAP.md` differs from the v12.4 snapshot because of the v12.4 addendum (the operator's change, made after that snapshot), and `system/CONVENTIONS.md` is over its ceiling (762 against 717), as recorded at v11.0. No file under `system/` and no protected file was changed for v12.5.

**Size:** COMMON +105 words; ORCHESTRATOR +570; advisor +400; author +185; librarian +140; proposer +57; reader +33; verifier +21. About +1,510 in all.

## v12.6 — 2026-10-16

**Round:** no new review. The operator's amendment in conversation with a session (session 5), made on 16 October with the deadline in view: V21 is being calibrated separately (his work); the machine's response to a review needed to judge in context and to carry the reviewer's detailed advice forward.

**Snapshot:** `history/machine/v12.5/` (taken now, before the change; v12.5 had none).

**Diagnosis:** (1) R-01 (`respond`) treated the reviewer's revision depth as a floor ("You may go shallower only by showing that the findings behind the depth do not hold") and knew neither the date, the deadline nor the competition, so a demanding reviewer set the route whatever the paper's chance or the time left; the controller was forbidden to judge. (2) The reviewer's detailed advice reached later calls only in part: R-01 compressed it into findings and a 500-word brief; `rewrite` gave L8 the full review, but `replan`, `rechoose` and `repropose` gave the proposer and author the brief alone (ORCHESTRATOR section 3; the L1 and L4 rows), so reformulated passages, a stronger paper inside the paper and named countercases were lost.

**Changes:**
- `lean/roles/advisor.md`, `respond`: the advisor makes the final call on the practical question (will it stand; its chance in the competition; what the time allows). Depth `abandon` is dispositive (only `repropose`, with a statement whether a new run can finish in time); every other depth is advice that may be overruled either way with reasons. A `send` or `local` review's points are weighed: `send` with up to three cheap, local fixes (`fixes: <n>`, a Fixes section), or `send` as it stands; a central-inference or novelty flaw is never a cheap fix. The advisor counts the time. New output `<rd>/advice-carried.md`: every concrete suggestion in the review and report, each marked adopt, adapt or decline with a reason.
- `lean/ORCHESTRATOR.md`: R-01 also reads the seed and is given the date, the seed's schedule and the round count; the controller does not second-guess it. `send` with fixes runs L8 `revise` limited to the Fixes, the word count and L9, with no further outside review; a time note and an `abandon` review are told to the operator plainly for his choice. `advice-carried.md` is copied to `prior/` on `replan`, `rechoose` and `repropose`, and is read by the proposer (L1), the author (L4, L8, `revise`) and the trial's T1; section 3 updated. Version lines.
- `lean/roles/author.md`, `revise`: reads `advice-carried.md` as a referee report; limited to the Fixes when the route note says so. `lean/roles/proposer.md`: weighs carried advice as it weighs briefs.
- Not changed: V21, V21-HARNESS-MAP, COMMON, STYLE, the drafter, reader and verifier (who still never see `prior/`), the review limit, the return, the stop rule, the trial and intake.

**Generality:** nothing names this paper's topic; the competition and dates come from the seed and the spawn message.

**Predicted effect:** a review that says send or local no longer forces a further round; a cheap fix gets made and the paper goes out. A reconceive review is weighed against the time left and may be answered with a stop-or-submit choice to the operator. Later runs begin from the reviewer's specific suggestions as well as the brief. Risks: R-01 may be lenient where the reviewer was right (the tests: the diagnosis's reasons against the review's tagged findings, and the next review's verdict on the changes); `send` with fixes skips an outside check of the fixed text (the verifier still runs).

**Earliest affected step:** R-01 of the next outside review round.

**Calls per run:** +0 (R-01 writes one more file); `send` with fixes: L8 and L9 replace a further review round.

**Oscillation:** amends v12.0 to v12.5's `respond` (the floor rule, from v12.0) and section 5 in place; reverses nothing added in v12.1 to v12.5.

**Size:** advisor about +380 words; ORCHESTRATOR +330; author +70; proposer +40.

## v13.0 — 2026-10-16

**Round:** no new review. The operator's change to the review loop, made in conversation with a session from his handoff (`V21-REFERENCES/record/CLAUDE-COMPARISON-HANDOFF.md`). It changes protected files (`system/PROTECTED.md`), so the version is major.

**Snapshot:** `history/machine/v12.6/` (taken before the change, with `_root/` copies of `V21-REVIEW.md`, `V21-HARNESS-MAP.md` and `CLAUDE.md`).

**Diagnosis:** the operator's calibration found standalone V21 reviews poorly calibrated against his judgments, and enlarging the rubric did not help. Short comparative readings against known references told accomplished work from a proposal whose central work was undone. A later rerun, with a few of his substantive standards added to the comparison prompt, handled scope better (the handoff, "Why this replaces the current review opening"). This supports a working method; it is not established general reliability.

**Changes:**
- `V21-COMPARE.md` (new, protected): the comparison-stage instructions for ChatGPT. The operator's working prompt, unchanged (checked against `record/COMPARATIVE-ASSESSMENT.md`), under a short header naming the five attached files, the candidate and the three references by title. The header tells ChatGPT to stop if a file cannot be read, to answer in the chat and to open nothing else. It does not mention the harness, the calibration or a later stage.
- `V21-REFERENCES/` (new, protected): the three reference manuscripts as supplied (`originals/`). Reading copies (`reading/`): `reference-B.doc` converted to `.docx` and checked against the binary (45 body paragraphs and 8 footnotes found); the identifying document-properties fields blanked in all three (personal name, institution, "Question 4"), with extracted text, notes included, unchanged. `record/` holds the handoff, the prompt and the publication-stage opening as supplied. `README.md` holds provenance and hashes.
- `V21-REVIEW.md` (protected): now the publication-stage file. The new opening says this judgment comes second and stops if `REVIEW/comparison.md` or its checksum is missing. Stage 1 is renamed "Publication judgment": it reads the paper, the frozen comparison and the references in `REVIEW/compare/`, still not the harness. New section 1a gives `PUBLICATION-JUDGMENT.md`'s opening and calibration table verbatim, with four lines of use (developed here, not supplied): the placement and calibration are starting evidence, to be checked and departed from with reasons; originality is for the literature check; the calibration, not a stricter standard, fixes what "ready" means; the references are not templates. Section 11 measures depth by the calibrated standard. Section 12 has the review say where the comparison placed the paper and whether the reviewer agrees. The front matter, the literature tags, the frozen review and Stage 2 (the architectural audit) are unchanged.
- `system/tools/review.py` (protected): `request` also builds `REVIEW/compare/`: exactly five files, refused if a reference or the prompt is missing. New `freeze`: copies `REVIEW/comparison.md` into the round folder, writes its sha256 to both places and makes the reviewer's copy read-only. It is refused if the comparison is already frozen or if `REVIEW/review.md` already exists. `collect` refuses without a frozen comparison, warns if it changed, and files the packet, the reviewer's copy and the checksum in `round-<n>/compare-packet/`. It deletes nothing.
- `lean/ORCHESTRATOR.md`, section 5: two verbatim messages to the operator (the upload-only comparison with web search off; then the publication judgment with web search on, in the same conversation if it can now see the folder, otherwise a new one). Between them, a step that saves a pasted comparison exactly and freezes it, with `waiting_detail: comparison | publication`. A blindness rule: the controller never runs or feeds the comparison. A deviation is logged if the comparison conversation had folder access or browsed. R-01 also reads `comparison.md`. Section 1 branch and version lines updated. `lean/roles/advisor.md`, `respond`: reads the comparison.
- `system/PROTECTED.md` (protected): lists `V21-COMPARE.md` and `V21-REFERENCES/`. `V21-HARNESS-MAP.md` (protected): a paragraph on the v13.0 cycle and v12.6's response. `START.md`, `CLAUDE.md`, `README.md`: The operator's steps and the pointer.
- Not changed: the comparison prompt's text, source intake (4a; the packet is built only from fixed files, so outside feedback cannot enter it), budgets, the review-round limit, stop rules, the one return, R-01's judgment rules (v12.6), manuscript production (L1 to L9).

**Why upload-only for the comparison:** the prompt was written for attachments ("all four attached manuscripts"). A conversation that can see this folder learns from its name and contents that the candidate is machine-made and comes from a harness. Both are among the things the handoff says to withhold. Uploads keep the first stage blind by construction, not by instruction.

**Generality:** nothing names this paper's topic. The references calibrate any candidate in the competition's general-journal frame.

**Predicted effect:** publication judgments anchored to the operator's calibration rather than to an unanchored demanding standard. Fewer `reconceive` verdicts on papers at or above the Reference A standard, and unchanged severity on papers at the Reference B level. Risks: one more step for the operator per round (the upload, then a freeze); if he continues the same conversation into Stage B, the comparator's own view anchors the publication judgment (permitted by the handoff; the frozen comparison still records the blind judgment); the references are a small calibration set. The test: the next rounds' depth against the comparison's placement, and the operator's agreement with both.

**Earliest affected step:** the next outside review's `request` (round 4 of paper-1, or the first round of a new lineage).

**Calls per run:** +0 subagent calls; per round, one more ChatGPT exchange and one `freeze`.

**Oscillation:** amends `V21-REVIEW.md` from v11.0 in place (the opening, section 1, a new section 1a, one sentence each in sections 11 and 12); reverses nothing.

**Size:** `V21-REVIEW.md` about +560 words; `V21-COMPARE.md` 650 (prompt 545); `review.py` +70 lines; ORCHESTRATOR +420; map +150; START +60.

**Gate and verification (2026-10-16):** `evolution.py check --from v12.6 --to v13.0` FAILs on exactly the protected files the operator authorized (`V21-REVIEW.md`, `V21-HARNESS-MAP.md`, `system/PROTECTED.md`, `system/tools/review.py`) and on `system/CONVENTIONS.md`'s size ceiling, which has been over since v11.0. It warns that ORCHESTRATOR (the version line, section 5's message) and advisor (`respond`'s reading line) amend paragraphs v12.6 added. These are amendments in place. The cycle was tested end to end on a scratch copy outside the machine folder, with round 3's paper as a stand-in, consuming no round. `collect` refused before a freeze. `request` built a packet of exactly five files, byte-identical to `V21-COMPARE.md` and the reading copies, with no calibration or harness text in it. `freeze` refused with no comparison, after a review was written, and on a second freeze. `collect` filed the review, report, comparison, checksum and packet, left `REVIEW/` empty, and warned when the comparison had been changed after the freeze. On the operator's mount `chmod` is ignored without error, so the checksum, not the file mode, is the freeze. The real `REVIEW/` was not touched.

## v14.0 — 2026-10-16

**Round:** no new review; v13.0 was never used. This is the operator's change, made the same evening in conversation with a session. It changes protected files (`V21-COMPARE.md`, `V21-REVIEW.md`, `V21-HARNESS-MAP.md`, `system/tools/review.py`), so by `system/PROTECTED.md` the version is major.

**Snapshot:** `history/machine/v13.0/` (the upload version, taken before the change).

**Diagnosis:** v13.0 kept the comparison blind by having the operator upload five files to an upload-only conversation, then save or paste its answer back. That was a nuisance every round. The operator asked whether the comparison could run inside the machine folder, with instructions to ignore the rest. The session advised against it. A conversation that can see the machine folder learns from its name and contents that the candidate is machine-made and that the other three papers are references in a test. Its comparison then no longer reads four papers on the same footing, and the calibration was presumably obtained blind. A lapse into `V21-REVIEW.md` would also expose the calibration table. The operator chose the middle path: a separate, neutrally named folder outside the machine folder holds only the packet, and ChatGPT reads it and writes there.

**Changes:**
- `system/tools/review.py` (protected): `request --packet <folder>` copies the five-file packet into the packet folder. It refuses a folder inside the machine folder or one that is not empty (Finder's `.DS_Store` ignored). `freeze --packet` takes that folder's `comparison.md` into `REVIEW/comparison.md` and freezes it as before. It then empties the folder: anything else the comparator wrote is kept in the round folder first, and every other file is checked by hash against the machine's copy before removal. If deletion is refused it says so, and the new `clear-packet` retries. Without `--packet` the v13.0 upload route still works.
- `V21-COMPARE.md` (protected): the header now says the five files are in this folder (or attached), that the prompt's "attached"/"uploaded" manuscripts are these four, to open nothing outside the folder, and to write `comparison.md` there as well as replying. The prompt below the header is still the operator's text unchanged (checked against `record/`).
- `lean/ORCHESTRATOR.md`, section 5: the packet folder (`~/Desktop/review-packet`; under `device_bash`, `$HOME/mnt/review-packet`). The session requests access to it, and permission to delete in it, once per session as needed. The two messages to the operator change: point a conversation at the packet folder only; then a new conversation on the machine folder.
- `V21-REVIEW.md` (one phrase), `V21-HARNESS-MAP.md` (the cycle paragraph), `START.md`, `CLAUDE.md`, `README.md`: the same, in a line each.
- Not changed: the prompt, the references, the calibration, the publication stage's method, R-01, intake, budgets, stop rules.

**Generality:** nothing names this paper's topic.

**Predicted effect:** per round, the operator points a ChatGPT conversation at one folder and says one line. He no longer uploads files or saves the answer. Blindness is unchanged from v13.0, still by construction (the comparator's folder holds only the packet). Risks: if ChatGPT's folder access reaches beyond the folder it is pointed at, blindness then rests on the "open nothing outside this folder" line, though the packet folder's own path reveals nothing about the machine. The session needs that folder connected, which costs one access prompt and one delete prompt per session that runs a review.

**Earliest affected step:** the next outside review's `request`.

**Calls per run:** +0.

**Oscillation:** amends v13.0's section 5 messages and the `V21-COMPARE.md` header in place; restores nothing older.

**Size:** `review.py` +60 lines; ORCHESTRATOR +110 words; `V21-COMPARE.md` +40.

**Verification:** tested end to end on scratch copies outside both folders, consuming no round.
- `request` refused a packet folder inside the machine folder and a non-empty one, wrote five files identical to `REVIEW/compare/`, and ignored a `.DS_Store`.
- `freeze` took the comparator's `comparison.md`, kept an extra file it wrote as `packet-extra-notes.txt`, and emptied the folder. With deletion refused, it froze, said what it could not empty, and `clear-packet` finished the job afterwards.
- `collect` filed everything and left `REVIEW/` empty, and the next round's `request` accepted the emptied folder.
- `evolution.py check` results follow below.

**Gate:** `evolution.py check --from v13.0 --to v14.0` FAILs on exactly the four protected files the operator authorized and on the old `system/CONVENTIONS.md` ceiling. Its oscillation warnings are v13.0's section 5 paragraphs and docstring, amended in place the same evening, before any round used them.

### Observed in round 4 of paper-1 (machine v14.0), 2026-10-17

v14.0 predicted that the operator would point a conversation at one neutral packet folder, that blindness would be unchanged, and that the comparison would be frozen without uploads. That happened: `comparison.md` is frozen with its hash, the packet copy sits in `compare-packet/`, and the comparison reads the four papers on one footing, never treating the candidate as machine-made. The review then used the comparison as its starting point and departed from it only on literature and one inference, which is what the calibration was meant to permit. The change worked as designed. It could not, and did not, touch novelty: the defects the review found entered at L2 and L5 under v12.4.

## v14.1 — 2026-10-17

**Round:** no new review. The operator's change, made in conversation with a session while the round-5 request for `runs/paper-1-r5` waited for its blind comparison. No protected file is changed, so the version is minor.

**Snapshot:** `history/machine/v14.0/` (taken now, before the change; v14.0 had none).

**Diagnosis:** Reading the round-5 paper, the operator found passages so dense that they took several readings, and a weak title. He then had ChatGPT read the paper for organization, style and clarity, and its notes confirmed both: the introduction surveys replies to quasi-realism before saying what quasi-realism is; several paragraphs do three or four jobs; quotations introduce ideas the paper should first state itself; an objection is voiced before it is flagged as one; shorthand verdicts ("the resource suffices", "loses a route") stand in for claims at the major transitions; and the PDF prints doubled section numbers ("1 1. Introduction"). The session traced the fault to the machine:
- Since v12.0 no call reads for prose. The v3–v11 wash (V16 selection), the whole-draft read with its LLM-pattern count (V17) and `system/norms/llm-patterns.md` and `editorial-norms.md` were dropped. `lean/STYLE.md` kept one prose paragraph. The cold reader (L7) reports prose stalls, but as one of six items, and on the draft, before the rewrite.
- After the last rewrite only argument checks (L8-03) and mechanical verification (L9, "change nothing else in the prose") run, so the text that goes out has never been read for clarity. In round 4, L8-05 rewrote 4,817 words, then L8-06 and L9-03 followed.
- The author cannot see this alone: knowing the argument's history makes unclear prose look clear. The reading must be fresh.
- The outside review cannot catch it: its perfect-prose test assumes perfect prose. Yet the blind comparison ranks the paper against reference manuscripts as written.
- The doubled numbers come from `lean/STYLE.md` (v12.0: "sections as `# 1. Title`") against a template that numbers sections itself (`system/render/README.md` always said `# Introduction`). No call looked at the PDF as a reader sees it.

**Changes:**
- `lean/roles/editor.md` (new): mode `clarity`. A fresh Opus reader that sees only the final paper, its own preview render and `lean/STYLE.md`. It reads twice (as a first reader, then as an editor) and writes one note per instance, each with a unique anchor copied from the Markdown and a ready-to-paste replacement. It also judges the paper's title and section titles (proposing two or three paper titles if it should change) and presentation (numbering, stray markup, footnotes, references, drafting residue). It keeps the genre's legitimate habits and lists model sentences. Exhaustive, but no invented problems. Adapted from the operator's ChatGPT prompt, extended for more interventions and concrete formulations.
- `lean/roles/author.md`: new mode `clarity`. A note stands unless the text answers it within a paragraph or the replacement would change a claim, quotation, citation or step. Each note gets `adopted`, `adapted` (what changed and why), `rejected` (with a reason) or `harness` (presentation problems outside the Markdown, reported to the operator). The author may narrow claims, never widen them. `cut`: delete, never merge sentences or pack clauses (restoring v3's rule), and keep clarity changes.
- `system/tools/clarity_check.py` (new): checks that every note has exactly one disposition, the counts match, every rejection, adaptation and harness item gives a reason, harness is used only for presentation notes, and every adopted note is visible in the paper.
- `lean/ORCHESTRATOR.md`: new section 4e. The clarity edit (E-01 editor, E-02 author, the check, one retry on failure, the word count and a cut) runs before every L9 except after `send` with fixes, whose text the reviewer already judged edited. Section 3 adds the editor's blindness. The table, routing and section 5 routes are updated. After L9 and after 4e, problems outside the Markdown are told to the operator. Section 5 gains "Withdrawing a request before the freeze". Section 7 adds step `E`.
- `system/tools/withdraw.py` (new): withdraws a request before the freeze. It refuses if the comparison is frozen or a review exists. It stops if the packet folder holds anything but packet copies (above all a written `comparison.md`, which the operator moves out himself). It empties the packet folder and moves `REVIEW/` into `round-<n>/withdrawn-<k>/`; the round number is unchanged.
- `lean/roles/verifier.md`: after rendering, inspects the PDF text (the first pages, headings, references) for numbering, stray markup, footnotes and residue. It fixes in the Markdown what the Markdown causes and lists other problems as `render_problems: <n>`.
- `lean/STYLE.md`: a clarity paragraph (the view before replies to it; the argument's shape in plain words before its exact form; one's own sentence before the supporting quotation; one job per paragraph; objections announced; claims, not shorthand, at transitions; distinct returns to the thesis; the genre's keep-list; delete, never merge; titles). Sections are now `# Title`, unnumbered.
- `system/render/render.sh`: warns on a numbered Markdown heading.
- Operator instructions (the operator's addition during the change: at some point a colleague should be able to run the machine). `lean/ORCHESTRATOR.md`, section 6: every message asking the operator to act is self-contained, with five parts: where things stand; numbered steps naming the app, folder and settings; the exact words to paste in quoted blocks; how they will know it is done; and what to say back, with how to start a new session. Every stop ends with the same, and `position` records the operator's next action. `START.md` is rewritten as a guide for someone new to the machine.
- Weighing machine changes (the operator's addition: the harness is now well calibrated, which should count when Claude assesses ChatGPT's architectural suggestions). `lean/roles/advisor.md`, `respond` (and the architecture section of `assess-lead`): the burden is on the change. Each recommendation, the reviewer's or the advisor's own, must name a failure in this run's record, quoted, not a general risk or a fault already answered in `EVOLUTION.md`. It must say whether that failure recurred, and what the change costs in calls, instruction length and confounding of the next measurement. `adopt` only for an observed, recurring failure met by a small, targeted change; `test` for thin evidence, naming what recurrence would justify it; `reject` otherwise, including checks or rules with no failure behind them. "No change" is a good outcome, with at most two adopts per round. `lean/ORCHESTRATOR.md`, section 5 step 6: The operator is told each note's mark and evidence, with `reject` and `test` presented as the default. The record shows why: ten versions in four days (v12.0 on 10-14 to v14.1 on 10-17), most changes untested before the next. The external architecture audit sees the machine fresh each round and is asked to find things, so it tends to propose additions.
- Not changed: V21 files, `review.py` and other protected files, the reader, drafter, advisor, budgets elsewhere, the review limit, the return and stop rules. `V21-HARNESS-MAP.md` (protected) still lists seven lean roles; the operator may add the editor.

**Generality:** nothing names this paper's topic. Every paper passes through L9, and every paper's author knows its history.

**Predicted effect:** the reviewed and submitted text is clearer on a first reading. ChatGPT's kind of notes (introduction order, split paragraphs, explanation before quotation) should no longer recur in clarity readings of a later paper. The PDF no longer doubles numbers. The blind comparison should place a polished paper no lower than the same argument unpolished; round 5 of paper-1, redone with the edited text, is a near-controlled test, since its argument is unchanged from the withdrawn request.

Risks:
- The editor's replacements may drift from the argument, mitigated by the author's dispositions, the narrowing-only rule and the verifier's quotation check.
- Clarity additions push length, so a cut may follow.
- A Claude editor may share the writer's blind spots. The test: compare E-01's notes with the operator's ChatGPT notes on the same paper.

**Earliest affected step:** E-01 of `runs/paper-1-r5` (the withdrawn round 5).

**Calls per run:** operator instructions +0. Clarity edit +2 per pass to L9 (E-01, E-02), +1 if the check fails, +1 if a cut is needed. A run with one outside review and one rewrite adds 4.

**Oscillation:** `evolution.py check --from v14.0 --to v14.1` warns that ORCHESTRATOR removes one paragraph v14.0 had just added: the opening paragraph listing the versions, amended in place to add v14.1 (with the version heading). Nothing is reversed or restored.

**Size:** ORCHESTRATOR 4,507 to 5,109 words; STYLE 286 to 452; author 696 to 1,072; verifier 158 to 280; editor 812 (new); tools +200 lines (two new scripts); render.sh +3 lines.

**Gate and verification:** the check FAILs only on `system/CONVENTIONS.md`'s size ceiling, over since v11.0, which v14.1 does not touch. Both new tools were tested on scratch copies outside the machine folder:
- `clarity_check.py` passed a correct response, and caught missing, duplicated and unknown dispositions, wrong counts, rejections or harness items without reasons, harness on a non-presentation note, and an adopted note not visible in the paper.
- `withdraw.py` emptied a packet of exact copies and moved `REVIEW/` into `withdrawn-1`, and refused a packet holding a `comparison.md`.
- `render.sh` passes `bash -n`.

### Observed in round 5 of paper-1 (machine v14.1), 2026-10-17

v14.1 predicted a text clearer on first reading, and a blind placement no lower than the same argument unpolished, with the withdrawn round 5 as the test. The first half is borne out: the review calls the prose "generally intelligible and unusually disciplined about attribution", and the verifier found no doubled numbering. The controlled test did not happen: the withdrawn request never reached a frozen comparison, and the move from round 4 (revise, structural) to round 5 (send, local) also follows the L8-05 argument rewrite, so it cannot be credited to the clarity pass. The named risk, editor replacements drifting from the argument, occurred in small form: N16 sharpened the Golub conflation, N5 shortened the condition to "the identity", N24 elaborated "every element is doxastic" without the commitment distinction. Each looked like clarification, so the narrowing-only rule passed them.

### Observed in a side study: paper-1-r2 re-checked under v13.0 to v14.1, 2026-10-17

Recorded at the operator's request; it changes no machine file and no run (`studies/r2-blind-recheck/README.md` has the record, hashes and both reviews). The question was whether the pre-v13 round-2 review was too severe and set the lineage on a needless path. A copy of r2's final paper, the text the round-2 reviewer read, went through the v14.1 clarity pass (E-01, E-02, E-03, L9-01) and then the v14 blind comparison and the publication judgment, in a packet folder that held no harness file. Stage 1 was saved before the reviewer was given the machine for Stage 2.

- **Placement:** above Reference B, "close to but somewhat below" Reference A, below Reference C. That is one rung below r5's rounds 4 and 5 (above Reference A, close to Reference C).
- **Verdict:** revise, `structural`, argument and literature, moderate confidence. Round 2 had said revise, `reconceive`, argument and significance, high confidence. The two reviews find the same two gaps (the "only if" restriction on explanatory obligations; the step from serviceable alternative contents to evidence of nearby error) and judge the metronome the same way.

This bears on v13.0's prediction ("fewer `reconceive` verdicts on papers at or above the Reference A standard"). On a paper just below that standard, the calibrated review took depth down one notch and dropped `significance` for `literature`, without changing the diagnosis. That notch mattered: round 2's depth floor made `rechoose` the shallowest response, and R-01 went to `repropose`, so repairing r2 was off the table. The later path still produced the better paper. The study does not show the lineage was misdirected, only that the old review over-called depth. Limits: one comparison, one review, written in the comparison's own conversation, on a polished text.

Two v14.1 observations from the same pass: `clarity_check.py` failed twice on false positives (a paragraph split whose anchor stays, and a hyphen-to-en-dash change read as a deletion), both confirmed in the text. L9-01 left the drafting mark `[from memory, unverified]` printed after a citation as a "render problem"; it was removed on the operator's word before the comparison.

## v14.2 — 2026-10-18

**Round:** no review. The operator's change, made in conversation with a session on 2026-10-18 when he asked for a new paper on a new topic. Paper-1's `runs/paper-1-r5` is waiting for submission (by 30 October) and is parked. No protected file is changed, so the version is minor.

**Snapshot:** `history/machine/v14.1/` (taken now, before the change; v14.1 had none).

**Diagnosis:** no diagnosis file. The operator asked for a new run: "I want the machine to write a paper that's focussed on the literature around Steve Petersens' 'Designing People to Serve'". The lean machine (v12.0 on) starts at L1, and L1 reads `00_seed/`, `01_region/region.md` and `02_corpus/`. For paper-1 those were made by the v3 opening (V00 to V03). Since v12.0 no lean step makes them, and `lean/ORCHESTRATOR.md` forbids the orchestrator to open the old step cards, so the lean machine could continue a lineage but not open one. `STATE.md` also held only one run, so a new lineage would have overwritten paper-1's state while it still waits for submission.

**Changes:** the operator's procedure, in his words: "Intake (V00): you and me in one conversation, no subagents. It produces the seed, the form settings (length, audience, format) and your taste examples. [...] I'd skip the old intake questions about the three 'voices', which lean doesn't use. Map the region (V01): one call, with web search. [...] Choose the region (V02): one fresh judge call. It picks a mid-sized region (two to four live questions sharing one literature), names four to six starting points and writes a first request of about fifteen sources. If it judges there's no paper worth fishing for, it says so before anything is spent. Gather sources (V03, second half only): three librarian calls in parallel, then one to merge. [...] I'd skip the voice setup and replace its check with 'each starting point has at least two core sources'. Anything unreachable comes to you once, as now. Then you start a new paper-2 run at its first step, unchanged."
- `lean/ORCHESTRATOR.md`: new section 4f, "Opening a new lineage". O0 is the intake, with the orchestrator and the operator and no subagent, and v3's V00 questions minus voices, dispositions and norms; it writes seed, seed-form and taste. O1 is one cartographer call (sonnet, high, web; budget 40). O2 is one advisor call, `region-check` (opus, high; budget 14), with one remap allowed. Then `requests.py harvest` and `batches --n 3`. O3 is three librarian `corpus` calls run at the same time, the one exception to "one at a time", then one `merge` call. A starting point with fewer than two core sources gets one more corpus call and merge. Unreachable texts go to the operator once (`requests.py checkpoint --step O3`). Then L1, unchanged. Section 1: READY may start at O0 to O3, and a parked run waiting for submission is mentioned at each session start. Section 6: the intake and the O3 offer are added to what the operator is asked. Section 7: steps O0 to O3, and a new state field `parked`.
- `lean/roles/cartographer.md` (new): modes `map` and `remap`, from v3's cartographer without `contact-map` (voices). The region-map template is now written inline. If the seed names a focal work, the cartographer maps the literature around it, reading the held text first.
- `lean/roles/advisor.md`: new mode `region-check`, from v3's judge-advisor `region-check`, the region-check criteria in `system/criteria/selection-criteria.md` and the `region.md` template, all inline. Added: a focal work fixes the literature, but the live disagreement must still run beyond it. "The voices find it" becomes "the proposer finds it".
- `lean/roles/librarian.md`: new modes `corpus` (v3's V03 `gather`: one batch, no shared files) and `merge` (v3's `merge`, with the voice check replaced by "each starting point has at least two core sources", and new requests for thin ones). Their output, `work/corpus.md`, has front matter the orchestrator routes on.
- `STATE.md`: field `parked`.
- Not changed: L1 to L9, the outside review, the V21 files, the tools. `new_run.py` still makes the v3 folder layout, and the empty v3 folders are harmless. `V21-HARNESS-MAP.md` (protected) does not list the cartographer or the opening; the operator may add them.

**Generality:** nothing names a topic. Every new lineage needs a seed, a region and a corpus. The focal-work clause applies whenever a seed names a work, which the operator's request for paper-2 is the first to do.

**Predicted effect:** a new lineage reaches L1 with a region and a corpus comparable to paper-1's (about fifteen sources, two core sources per starting point) in five or six calls rather than v3's six or more plus voice setup. Risks: (1) a focal work may draw the region too close to one chapter. The advisor's clause guards against this, and the outside review's literature judgment will show it. (2) Parallel librarian calls write separate batch files, as in v3, which had no collisions. (3) Applied ethics is a new field for the machine, and the operator kept the metaethics taste file (his choice at intake). The advisor reads it as indications of form, as the file itself says.

**Earliest affected step:** O0 of `runs/paper-2`.

**Calls per run:** +0 for continuing runs. A new lineage: +5 (O1, O2, three corpus, merge: 6 calls), +2 if remapped, +2 if a starting point is thin, +1 if the operator supplies texts.

**Oscillation:** `evolution.py check --from v14.1 --to v14.2` warns that ORCHESTRATOR removes three paragraphs v14.1 had just added and advisor one. All four are amended in place, not reversed: the heading line and opening paragraph (now naming v14.2), section 1's branch line and session-start line (O0 to O3 and the parked run), section 6's list of what the operator is asked, section 7's step and field lists, and the advisor's role-title line. Nothing is restored.

**Size:** ORCHESTRATOR 5,398 to 6,244 words; advisor 2,888 to 3,297; librarian 886 to 1,425; cartographer 427 (new).

**Gate and verification:** the check FAILs only on `system/CONVENTIONS.md`'s size ceiling, which has been over since v11.0 and which v14.2 does not touch. It also FAILed on the Oscillation field until the field was answered above.

## v14.3 — 2026-10-18

**Round:** no review. The operator's rule, given in conversation on 2026-10-18 after the O3 source offer for `runs/paper-2`. No protected file is changed, so the version is minor.

**Snapshot:** `history/machine/v14.2/`.

**Diagnosis:** the operator (verbatim): "new rule: always include doi when you make lit requests". The O3 offer listed 13 texts, and only 5 carried a DOI. The librarian's `gather` and `merge` instructions asked for a full reference and a file name, and nothing required a DOI (only `intake` asked for "a stable identifier"). One DOI the librarians recorded was wrong: R-010's 10.1093/0195150430.003.0007 for Mele 2006 chapter 7. Crossref gives 10.1093/0195305043.003.0007 ("My Compatibilist Proposal", pp. 163-198).

**Changes:**
- `lean/roles/librarian.md`: a rule at the top, covering every mode. Every text sent to the operator carries its DOI, checked against the DOI's own record and not copied from a search result. A chapter takes the chapter's DOI, else the book's. A text with no DOI says "no DOI" and gives its best stable identifier. It is named in `gather` item 2 and in `merge`'s for-operator resolution.
- `lean/ORCHESTRATOR.md`, section 6: every text asked of the operator carries its DOI (or "no DOI" and a stable identifier). The orchestrator looks up a missing one before sending, as a mechanical step.
- Not changed: `requests.py checkpoint`, which prints what the requests hold. The orchestrator composes the operator's message, and section 6 governs that message.

**Generality:** applies to every request to the operator in every lineage.

**Predicted effect:** every text the operator is offered can be found from its DOI in one step, and a wrong DOI is caught when it is checked against its own record. Cost: a Crossref lookup or two per unreached text.

**Earliest affected step:** the DOI addendum to paper-2's O3 offer (sent today), then every later request.

**Calls per run:** +0.

**Oscillation:** the check warns that ORCHESTRATOR removes one paragraph v14.2 had just added and librarian two. All three are amended in place, not reversed: the heading and opening paragraph (now naming v14.3), the librarian's title line, and the `merge` paragraph (the DOI added to the for-operator resolution). Nothing is restored.

**Size:** librarian +78 words; ORCHESTRATOR +45.

**Gate and verification:** the check FAILs only on `system/CONVENTIONS.md`'s size ceiling, which has been over since v11.0 and which this change does not touch.

## v14.4 — 2026-10-18

**Round:** no review. The operator's rule, given in conversation on 2026-10-18 while `runs/paper-2` waited for its blind comparison. No protected file is changed, so the version is minor.

**Snapshot:** `history/machine/v14.3/`.

**Diagnosis:** the operator (paraphrased): the prose of the papers is reasonably good, but the abstracts are too dense and do not follow the conventions of an abstract. The machine had no step for it. `lean/STYLE.md` and the author's `rewrite` mode set only a ceiling of 150 words and a condition that a conditional result be stated as conditional; the clarity editor (v14.1) checked only that the abstract "does not match the body" and that its promise is not larger than the body's. Nobody was told to read the abstract as a first-time reader or to edit it. The paper-1 and paper-2 abstracts compress a whole inference chain into five or six long sentences, use terms of art undefined (corrigibility, non-domination, the "2023 successor"), and give no plain statement of the problem before the thesis.

**Changes:**
- `lean/STYLE.md`: a paragraph, "The abstract", fixing the convention: order (problem and target, thesis in one plain sentence, main steps, upshot), plain terms, at most one other name, no quotations or citations, no shorthand verdicts or unintroduced labels, sentences of about 30 words at most, nothing beyond the body, gist rather than a compressed introduction.
- `lean/roles/editor.md`, `clarity`: an abstract pass after the two readings. Unless the abstract already meets every item, the editor writes one note of kind `abstract` whose Replacement is a full new abstract (at most 150 words), using only claims, terms and names the body has. A new front-matter field `abstract: <revised | kept>`.
- `lean/roles/author.md`, `clarity`: an adopted or adapted `abstract` note replaces the whole field, written as a YAML block, at most 150 words, every term and claim found in the body.
- `lean/ORCHESTRATOR.md`: heading and section 4e name the abstract. `STATE.md`: version.
- Not changed: `system/tools/clarity_check.py` already takes any note kind and checks adoption by the replacement's opening words; the abstract note passes through it as it is.

**Generality:** nothing names a topic. Every paper has an abstract and passes the clarity edit before verification.

**Predicted effect:** the abstract of every paper is read cold by an editor, rewritten to the convention and checked against the body before the PDF is made; abstracts that were dense in the previous papers should come out as a plain problem, thesis, route and upshot. Risks: (1) a cold editor may simplify away a hedge; the author's rule (nothing wider than the body) and the L9 read guard this. (2) A plain abstract is longer in sentences, so it can press on 150 words; the word count then governs.

**Earliest affected step:** the clarity edit (section 4e) of `runs/paper-2`, or of any paper after a `revise`. Not applied to a paper already sent out for the blind comparison unless the operator withdraws that request (section 5).

**Calls per run:** +0.

**Oscillation:** the check warns that ORCHESTRATOR removes one paragraph v14.3 had just added. It is amended in place, not reversed: the opening paragraph (now naming v14.4's abstract edit) and the heading line. Nothing is restored. The editor's and author's clarity modes only gain text.

**Size:** STYLE about +170 words; editor +190; author +50; ORCHESTRATOR +20.

**Gate and verification:** see the check run below.

## v14.5 — 2026-10-18

**Round:** no review. The operator's rule, given in conversation on 2026-10-18, minutes after v14.4, when he asked whether a paper that goes out after the outside review gets the abstract edit. No protected file is changed, so the version is minor.

**Snapshot:** `history/machine/v14.4/`.

**Diagnosis:** v14.4 put the abstract edit inside the clarity edit (section 4e). Section 5 skips that edit after a `send`, with or without fixes, because the reviewer judged the edited text. So the papers that go out are exactly those whose abstract is never edited by the new step: a `send` ships the abstract as it was. The operator's concern is that the abstract is the part a reader meets first, and its fault (density, no convention) is not something an outside reviewer's judgment of the argument clears.

**Changes:**
- `lean/ORCHESTRATOR.md`: section 4g, the abstract-only pass, run after every `send` (after the fixes and their word count, before L9). Three new call rows in the step table. Section 5, After, step 5, `send`: both branches name it. The "Before L9" bullet and the heading are updated.
- `lean/roles/editor.md`, mode `abstract`: reads only the final paper and `lean/STYLE.md`; writes at most one `abstract` note, or says `kept`.
- `lean/roles/author.md`, mode `abstract`: changes the `abstract:` field and nothing else.
- `lean/roles/advisor.md`, mode `abstract-check`: a fresh call compares the paper before and after, confirms that only the abstract differs, and refuses any claim the old abstract did not make, any dropped hedge or condition, and any term the body does not use. On a second `no`, the earlier version is put back and the operator is told.
- Not changed: `clarity_check.py` (reused with the abstract files), the review itself, the clarity edit of v14.4.

**Generality:** nothing names a topic. It applies to every `send`.

**Predicted effect:** a paper that earns `send` goes out with an abstract that follows the convention, without a second outside review and without any change to its body or title. Risks: (1) the reviewer did not read the new abstract; the check guards that by refusing anything wider than the old one. (2) A plainer abstract is easier to read but may state the thesis more bluntly; the check compares hedges. (3) If the editor keeps a good abstract, nothing changes, and no L9 is run for it.

**Earliest affected step:** the `send` branch of section 5 for the paper now waiting on its first outside review (`runs/paper-2`), and any later `send`. The parked `runs/paper-1-r5` was sent before this rule; it takes the pass only if the operator says so.

**Calls per run:** +3 after a `send` (editor, author, check), +1 when the check says `no`, +0 otherwise. L9 runs again after a changed abstract.

**Oscillation:** the check warns that ORCHESTRATOR removes one paragraph v14.4 had just added. It is the opening paragraph, amended in place to name v14.5 (and the heading line). Nothing is restored; v14.4's text elsewhere is kept.

**Size:** ORCHESTRATOR +420 words; editor +230; author +190; advisor +250.

**Gate and verification:** see the check run below.

### Observed in round 1 of paper-2 (machine v14.5), 2026-10-18

v14.5 predicted that a paper earning `send` would go out with a conventional abstract after an abstract-only pass. This round returned `revise`, so the pass did not run: no evidence either way. The judged abstract's fault is overclaim, which only the replan repairs.

## v14.6 — 2026-10-18

**Round:** after round 1 of paper-2 (machine v14.5). The operator adopted, in conversation on 2026-10-18, the two machine notes R-01 marked `adopt` in `runs/paper-2/10_review/round-1/diagnosis.md` (Machine notes 1 and 3; architecture report R1, narrow form, and R5, parser fix only). The rest (R2, R3, R6 test; R4 and the deadline sentence reject) were not adopted.

**Snapshot:** `history/machine/v14.5/`.

**Diagnosis:** (1) The round's only reject-level finding was a central argument written new at L8-04 (the confinement argument), listed under "Still weak" in its rewrite note, yet marked `central_weak: no`; and the L8-04 route after a final check's `revise` went to the clarity edit and L9 with no second check. A new or weak central argument therefore reached the outside reviewer untested. (2) `clarity_check.py` matched only a bare `^Replacement:` line, so a labelled replacement parsed as empty and was treated as a deletion (N20 in paper-2; E-03 spent 78,232 tokens answering a false problem).

**Changes:**
- `lean/roles/author.md`, mode `rewrite` (and every mode that writes the rewrite note): `central_weak: yes` also whenever the call writes a central argument no earlier check has read, or lists a central step as still weak.
- `lean/ORCHESTRATOR.md`, section 4, After L8: after L8-04, read `central_weak:`; `yes` spawns one fresh final check; its `go` leads on, its `revise` gets one author call that only shrinks claims (no inference added) and then no further check, its `sources` and `rechoose` route as before. Section 5, `rewrite`: the same fresh check before the clarity edit when the rewrite note says `central_weak: yes`. Title and opening paragraph name v14.6.
- `system/tools/clarity_check.py`: the Replacement label may be bold, prefixed or qualified before the colon; a note with no parseable Replacement is a schema error, never a deletion. Verified: the v14.5 tool reports "N20: adopted as a deletion" on paper-2's E-02 files; the v14.6 tool passes them (43 notes); an unlabelled replacement is reported as a schema error.
- Not changed: the one-call editing variant of R5, the source-check route (machine note 2), corpus breadth.

**Generality:** nothing names a topic. It applies to every rewrite note and every clarity check.

**Predicted effect:** a paper whose rewrite introduces or leaves weak a central step gets a fresh critic before release; clean runs are unchanged. No false deletion alarms from the clarity check. Risks: (1) authors may over-flag, adding a call; (2) the shrink-only author call after a second `revise` could leave a thin paper, which the outside review will see.

**Earliest affected step:** L8 of `runs/paper-2-r2` (the replan now at L4), and its clarity edit.

**Calls per run:** +1 (sometimes +2) only when a rewrite note says `central_weak: yes` after L8-04 or after an outside-review rewrite; +0 otherwise. One fewer wasted retry when a replacement label varies.

**Oscillation:** the check warns that ORCHESTRATOR removes three paragraphs v14.5 had just added. They are amended in place, not removed: the title line, the opening paragraph (extended to name v14.6) and the After-L8 and section 5 `rewrite` lines, each with the v14.6 clause inserted. Nothing of v14.5 is undone. The L8-04 "no second check" sentence was a v13 choice, now replaced for the `central_weak: yes` case only.

**Size:** ORCHESTRATOR about +150 words; author +60; clarity_check.py +8 lines.

**Gate and verification:** `evolution.py check --from v14.5 --to v14.6` FAILs only on `system/CONVENTIONS.md`'s size ceiling, over since v11.0 and untouched here (byte-identical to v14.5), once the Oscillation field is answered. The tools compile; the parser fix was tested on paper-2's E-02 files and on a scratch notes file outside the machine folder, as recorded under Changes.

### Observed in round 2 of paper-2 (machine v14.6), 2026-10-20

v14.6 predicted a fresh critic for any new or weak central step, clean runs unchanged, and no false deletion alarms. Consistent: L8-01's new criterion went to L8-03, L8-04 reported `central_weak: no`, no second check ran, and the review found no reject-level fault (round 1: one). No false deletions; a different false alarm (structural notes N1-N3) occurred. Not attributable to v14.6 alone: replan, plan-check split, sources and rewrite changed together, and the residual faults are of scope, which v14.6 does not target.

## v14.7 — 2026-10-20

**Round:** none. The operator's design, adopted in conversation on 2026-10-20 (a design session, alongside the session running paper-2-r2): a final polish for papers he has chosen to submit. Not prompted by a review finding.

**Snapshot:** `history/machine/v14.6/`.

**Diagnosis:** Papers that have passed the outside review still read as if their author expects the reader to know the literature: names in quick succession at the opening, contemporary philosophers given by surname as if they were Hume or Kant, works not named, condensed passages and examples whose point the reader must work out. The clarity edit (v14.1) is a Claude reader and a Claude author; the operator wants, as the very last step, a different strong model reading the whole paper at once with cognitive empathy for the reader, followed by a Claude check that keeps only edits that change nothing the paper says. The prize's word limit is 6,000; the operator's reading (2026-10-20, the call for papers being silent) is that notes count and the bibliography does not, which leaves a cushion the machine's conservative 5,500 all-in rule does not use.

**Changes:**
- `POLISH-PROMPT.md` (new, top of the machine folder; the operator's to change): the polisher's instructions. Cognitive empathy with a philosopher outside the debate; people introduced by full name and, where it helps, the work, at first mention; lists of names turned into introductions; condensed passages unpacked; examples made explicit; transitions. Hard limits: no drift in modals, quantifiers, scope, hedges, conditionals, self-description or objection strength; no new content; names and titles only from the References list (placeholders otherwise); title, abstract, headings, quotations, citations, notes, numbered labels, References and Markdown conventions kept; no inflation; a word budget.
- `system/tools/polish.py` (new): `request` archives `09_final/` in `12_polish/pre-polish*`, counts body, headings and notes, sets the budget at min(baseline × 1.15, 5,800), fills the prompt and copies `POLISH.md` and `paper.md` into `~/Desktop/polish-packet`; `collect` files the reply (folder or pasted), splits off the editor's notes and writes `12_polish/compare.md`, an aligned paragraph-and-note comparison flagging dropped and added text, changed hedge, modal, quantifier and self-description words, altered quotations, moved note markers and new names; `check` gates the reviewed text (title, abstract, headings, notes, references and every quotation as before; no placeholders; within budget). `compare` and `count` stand alone.
- `lean/roles/advisor.md`: mode `polish-review`. Asymmetric: accept by default, revert any content change, fix errors, verify every introduced name against the References or `02_corpus/bibliography.md`, restore anything dropped, add no edits of its own; writes `09_final/final.md` by script from the files and `12_polish/polish-review.md`.
- `lean/ORCHESTRATOR.md`: section 4h, the final polish (only on the operator's word, for a run waiting for submission, current or parked; request, the polisher, collect, P-01, the check with one repair call and a fallback to the pre-polish text, L9 again with no cut, deliver); section 3 (who sees what), section 1 (branch on `waiting_for: polish`), section 6 (the operator is asked to run the polish only when he has asked for it), section 7 (`step: P`, `waiting_for: polish`). Title and opening paragraph name v14.7.
- `system/tools/README.md`: the `polish.py` row. `STATE.md`: `machine_version`, and `polish` among the `waiting_for` values.
- Not changed: the 5,500 rule for every other step, the clarity edit, the outside review, the abstract-only pass.

**Generality:** nothing names a topic or a paper. It applies to any run waiting for submission, on the operator's word.

**Predicted effect:** submitted papers that introduce their interlocutors and unpack their compressed steps, with no change of claim. Risks: (1) the polisher varies terms or softens hedges in ways the comparison does not flag; the review reads every pair, not only the flagged ones; (2) one model's habits replace another's; the review reverts edits clearly worse for the reader, and the prompt names the habits; (3) an introduced name or title is wrong; only names in the bibliography survive; (4) the outside reviewer's judgment was of the unpolished text; the polish may change wording only, and the pre-polish version is kept.

**Earliest affected step:** a polish the operator asks for, after the abstract-only pass and L9 of a `send`.

**Calls per run:** +1 (sometimes +2) and one L9, only for a polished run; +0 otherwise.

**Oscillation:** the check warns that ORCHESTRATOR removes one paragraph v14.6 had just added. It is amended in place, not removed: the opening paragraph, extended to name v14.7 (as v14.6 extended v14.5's). Nothing of v14.6 is undone. Section 4g's rule that after a `send` only the abstract changes is kept, with the polish named as its one exception, on the operator's word.

**Size:** ORCHESTRATOR about +900 words; advisor +640; POLISH-PROMPT.md 1,090; polish.py about 400 lines.

**Gate and verification:** `evolution.py check --from v14.6 --to v14.7` FAILs only on `system/CONVENTIONS.md`'s size ceiling, over since v11.0 and untouched here, once the Oscillation field is answered; it does not list `POLISH-PROMPT.md`, a new file at the top of the machine folder. The tools compile. Tested on scratch copies of paper-1-r5's final text outside the machine folder. `compare` of the paper against itself: no flags. Against a copy with six planted edits (a dropped "at least", "I argue" made "I show", a quotation's capitals changed, an invented first name, a lost note marker, one harmless clarity edit): every planted change flagged, the harmless edit shown only as a CHECK line. `check`: fails on the unreviewed drift (note marker, quotation), passes once it is reverted with the clarity edit kept. `request` refuses a second polish and a non-empty packet; `collect` handles both a written file and a pasted reply wrapped in a code fence. Paper-1-r5 has room for 715 words; paper-2-r2 for 740.

### Observed in round 1 of paper-4 (machine v14.7), 2026-10-22

v14.7 (the final polish) predicted interlocutors introduced and steps unpacked with no change of claim; it has not run on this paper, so there is nothing to compare. v14.6's routing worked as designed (`central_weak: yes`; L8-03 read the cap) but the critic cleared the step, which became the one reject-level finding.

## v14.8 — 2026-10-22

**Round:** none. The operator's change, made in conversation on 2026-10-22 before any polish had run on a real paper. Not prompted by a review finding.

**Snapshot:** `history/machine/v14.7/` (with `POLISH-PROMPT.md` in `_root/`).

**Diagnosis:** v14.7 read the prize's word limit (6,000, bibliography excluded, everything else included) as leaving title and abstract uncounted, and then set the polish budget at min(baseline x 1.15, 5,800). The detailed rules say the count includes everything except the bibliography, so the title and abstract (about 160 words) belong in the count; the 5,800 safety line was in effect the limit less that cushion, and the 15 percent cap held the shorter papers well under it. The operator: the margin was hard to trust, and the budget should be the limit.

**Changes:**
- `system/tools/polish.py`: `counted` is title + abstract + body + headings + notes (references excluded); the budget is the limit, 6,000, for `request`, `count`, `compare` and `check`; the safety line and the growth factor are removed. The counter is unchanged and still takes the higher of two counts, which is the only margin.
- `POLISH-PROMPT.md` (the operator's, changed on his word): constraint F states the hard limit, what counts, and that title and abstract count though they stay unchanged.
- `lean/ORCHESTRATOR.md`: the length sentence of section 4h; title and opening paragraph name v14.8. `STATE.md`: `machine_version`. `system/tools/README.md`: the `polish.py` row.
- Not changed: a run is polished once; what the polish may and may not touch; the 5,500 rule for every other step.

**Generality:** nothing names a topic or a paper.

**Predicted effect:** more room for the polisher on every paper (paper-4: 635 words; paper-2-r2: 881; paper-1-r5: 1,074). Risk: a longer paper, as the polisher fills room it was not asked to fill; the prompt says not to, the review keeps only what helps the reader, and `check` fails any text over 6,000. A second risk is that another counter reads a few words more than this one.

**Earliest affected step:** a polish the operator asks for.

**Calls per run:** no change.

**Oscillation:** the check warns that ORCHESTRATOR (the length sentence and the opening paragraph), the tools README row and `polish.py` (the counting rule, its constants and their uses) remove text v14.7 had just added. All three are amendments in place of one rule, v14.7's 5,800 safety line and 15 percent cap, which the operator has reversed on his reading of the prize's rules (the count includes title and abstract and the bibliography alone is excluded); nothing else of v14.7 is undone, and the polish itself, its constraints and its review are as they were.

**Size:** ORCHESTRATOR about +30 words; POLISH-PROMPT +30; polish.py about -10 lines.

### Observed in round 1 of paper-5 (machine v14.8), 2026-10-23

v14.8 (the polish budget made the 6,000-word limit, title and abstract counted) predicted more room for the polisher on every paper, with the risk of a longer paper. No polish has run on paper-5, so there is nothing to compare. The v14.6 routing again worked as designed (L8-01 flagged the new framing, L8-03 ran), and again the critic cleared the step that became the reject-level finding, as in paper-4 round 1 (EVOLUTION, v14.7 entry: "the critic cleared the step, which became the one reject-level finding").

### Observed in round 2 of paper-5 (machine v14.8), 2026-10-23

v14.8 (2026-10-22) made the polish budget the 6,000-word limit with title and abstract counted, predicting "more room for the polisher on every paper", with the risk of a longer paper, and relying on the counter's "higher of two counts" as the only margin. No polish has run on paper-5, so the prediction cannot yet be compared. But this round shows the margin fails on a mathematical paper: `polish.py count` on 09_final/final.md reports "Counted ... 3380" and "Polish budget: 6000 (room for 2620 words)", while the verifier's corrected all-in count is about 5,471. Both of the counter's counts lose the text between a bare `<` and the next `>`. A polish run on this paper under v14.8 would be told it has about 2,600 words of room it does not have, and `check`, using the same counter, would pass a text over the limit.

## v15.0 — 2026-10-23

**Round:** paper-5 round 2 (R-02's machine notes 1 and 2; the architecture report's R4 and R1). Adopted by the operator in conversation on 2026-10-23. It changes a protected file, `system/tools/wordcount.py` (PROTECTED.md, item 5: the conservative word count), on the operator's explicit adoption of the counter repair, so by `system/PROTECTED.md` the version is major.

**Snapshot:** `history/machine/v14.8/`.

**Diagnosis:** (1) The word counter undercounted any paper with a bare `<` in its mathematics: its tag filter `<[^>]+>` read the `<` of an inequality as the start of an HTML tag and dropped all the text up to the next `>`, and it dropped a title or abstract outright if it contained `<`. On paper-5 it reported 3,560 to 3,620 words against a true count of about 5,480; `polish.py`, which uses the same counter, would have offered about 2,600 words of room where there were about 500, and its `check` would have passed a text over the limit (EVOLUTION, observed in round 2 of paper-5; deviations in runs/paper-5 at L8, E and R). The clarity check could not see a paragraph split, so a correctly made structural note failed and cost an author call that changed nothing (paper-5 E-05). (2) The final check named the abstract's inferences and tested their parts, then applied its tests "to the thesis the paper actually establishes, not the one it advertises", so an advertised conclusion stronger than what holds could pass: paper-5 round 1 (horizon necessity cleared by L8-03, the reject-level finding) and paper-4 round 1 (the simplicity cap advertised as general, cleared by its final critic). R-01 marked this adopt in round 1; it had not been made.

**Changes:**
- `system/tools/wordcount.py`: `<` and `>` inside math (`$...$`, `$$...$$`, `\(...\)`, `\[...\]`) are neutralized before markup is stripped; only a well-formed tag (`<name ...>`, `</name>`) is stripped; title and abstract are counted even when they contain `<`. `--selftest` runs five regression cases. Paper-5 now counts 5,480 (all-in) and 5,300 by the polish rule; paper-4, paper-2-r2 and paper-1-r5 count exactly as before.
- `system/tools/clarity_check.py`: an adopted note whose replacement is a paragraph operation ("new paragraph", "paragraph break", "end the paragraph", "split ... paragraph") also passes when a paragraph of the paper begins at its anchor; the existing visibility tests are unchanged and still apply first. On the four current finals the old check failed three (paper-5 N1, paper-2-r2 N1 to N3, all paragraph splits made as asked) and the new one passes all four; a paper with the split paragraph re-joined fails.
- `lean/roles/advisor.md`, mode `final-check`: the advisor first writes down the strongest conclusion the title, abstract and conclusion advertise, read literally (quantifiers, modals, parameters, assumptions), and tests it as advertised with the plainest countercase inside the paper's own permitted assumptions (its parameter space, or the nearest relevant alternative reading), then the abstract's inferences (at most three); a failing claim is narrowed and the narrowed claim tested. `go` now requires the advertised conclusion to be scoped to what holds. The sentence that applied the tests to the established rather than the advertised thesis is removed.
- `lean/ORCHESTRATOR.md`: title and opening paragraph name v15.0. `STATE.md`: `machine_version`. `system/tools/README.md`: the `wordcount.py` row; a `clarity_check.py` row added.
- Not changed: the routing after a failed clarity check (the architecture report's proposal to route checker faults to a deterministic diagnosis rather than an author retry); the 5,500 rule; `polish.py` itself, which inherits the repair; REVIEWS.md and earlier logs, which keep the low figures as recorded.

**Generality:** nothing names a topic or a paper; the counter repair applies to any text with mathematics, the final-check change to any paper.

**Predicted effect:** correct length gates and polish budgets on papers with inequalities; no false clarity-check failures (and no wasted author call) for paragraph splits; the final check catches an advertised quantifier or necessity claim that outruns the argument before the outside review does, with the risk that it presses a literal reading of a claim the paper plainly hedges, or asks to narrow a valid conditional contribution (the architecture report's false-hold risk).

**Earliest affected step:** any word count (L8, E, L9, R request, polish); the next clarity check; the next L8-03.

**Calls per run:** no change; one fewer author call when a structural note would have failed the old check.

**Oscillation:** the check warns that `lean/ORCHESTRATOR.md` removes a paragraph v14.8 had just added: it is the opening paragraph, amended in place to name v15.0 after v14.8's clause, which is kept word for word; nothing of v14.8's rule is undone. The final-check paragraph replaces wording that dates from v12.2's tests of the central inference; v14.6 routed more papers to the final check but did not change what it tests. Nothing earlier is undone.

**Size:** advisor.md about +70 words; wordcount.py about +30 lines; clarity_check.py +5 lines; ORCHESTRATOR about +25 words.

**Gate:** `evolution.py check --from v14.8 --to v15.0` FAILs on exactly the protected file the operator authorized (`system/tools/wordcount.py`) and on `system/CONVENTIONS.md`'s size ceiling (762 words by the gate's count, against 717), which is unchanged here and has been over since before v13.0. `wordcount.py --selftest` passes; both tools compile; the clarity check passes on all four current finals.

## v15.1 — 2026-10-23

**Round:** none. The operator's design, adopted in conversation on 2026-10-23, after he read the candidate papers and found a rushed, monotone quality that a line edit cannot reach: the moves are all there, but delivered at one pitch, written as if for another AI. Not prompted by a review finding.

**Snapshot:** `history/machine/v15.0/` (with `POLISH-PROMPT.md` and `CLAUDE.md` in `_root/`).

**Diagnosis:** (1) The v14.7 polish works sentence by sentence and keeps the structure, so it cannot fix pacing: whether a paper sets up its reveals, gives them room and makes their significance obvious, and spends its words in proportion to their importance. (2) The packet flow (one polish per run, run by the machine, the polisher blind to the folder) suits a machine step, not the operator's plan: run both polishes on every candidate, read them, and choose. The packet's blindness also kept the polisher from the sources it needs to extend a quotation or settle what a passage claims. (3) Every final paper was `paper.pdf`, so four candidates and their versions could not be told apart.

**Changes:**
- `POLISH-PROMPT.md` renamed `POLISH-LINE.md` (the operator's prompt, changed on his word): it runs in the machine folder on the run the operator names, may read anything there (names and titles also from the run's bibliography), and writes and renders `<run>/12_polish/<title> (line polish).md`. Its constraints are unchanged.
- `POLISH-STRUCTURE.md` (new, the operator's): the structure polish. It has fixed ingredients (title, conclusion, every move with its qualifications, the References; quotations kept, dropped or extended verbatim from the sources; the abstract only as the new order requires) and the warning that emphasis must come from placement and space, never from stronger claims. It works in five stages, written to its notes: understand (the argument, a numbered inventory of moves, the present outline); reflect (narrative desiderata: the question by page one, reveals set up and given room, space in proportion to importance, hand-offs, one voice, a conclusion that lands); decide (leave, re-pace or restructure, as an open question, with a new outline carrying every move); write; and check (every move at its strength).
- `system/tools/polish.py`: `name`, `render` (anonymous, into named `.tex`/`.pdf` with a copy in `PAPERS/`), `shelf` (names each candidate's `09_final` PDF `<title> (<stage>).pdf`, renders pending polishes, writes `PAPERS/README.md`), `file-reply`, `adopt`, `revert`, and `check` with structure rules (title, references and note markers kept; dropped and new quotations listed for the review and L9). `request`, `collect` and `clear-packet` are removed with the packet flow.
- `lean/roles/advisor.md`: mode `structure-review`. It builds its own inventory of moves before reading the editor's, finds each one (kept, compressed, drifted, missing), removes anything new, checks new quotations against sources and introduced names against the bibliography, repairs with the least change, and returns `adopt` or `reject`.
- `lean/ORCHESTRATOR.md`: section 4h rewritten (the two prompts are the operator's to run; naming and `shelf`; adoption only on his choice, with review, check, revert, L9 and delivery). Section 3's polisher line; `shelf` after a `send`; section 6 (the operator is never asked about polishes); the `polish` state retired. Title and opening paragraph name v15.1.
- `system/tools/methodology.py`: lists the named final PDF. `system/tools/README.md`: the `polish.py` row. `CLAUDE.md`: a pointer for an outside polisher. `STATE.md`: `machine_version`, and paths to the named PDFs.
- Renamed: `09_final/paper.pdf` and `paper.tex` of runs paper-1-r5, paper-2-r2, paper-4 and paper-5, to `<title> (pre-polish)`. `PAPERS/` is new.
- Not changed: L9 still renders `paper.pdf` (the verifier and `review.py`, protected, expect it); `shelf` names it once a run waits for submission.

**Generality:** nothing names a topic or a paper.

**Predicted effect:** papers whose turns are visible: the thesis known on page one, reveals set up and given room, and space in proportion to importance, with every move at its original strength. Risks: (1) emphasis rendered as inflation; the prompt forbids it, and the structure review's own inventory catches drift; (2) a restructure that drops a qualification as clutter; qualifications are named as part of the move, and the review restores them; (3) the outside review judged the pre-polish structure, so its verdict does not transfer; the operator reads both versions before choosing, and the pre-polish version is kept; (4) with access to the whole folder, the polisher could import material from plans or reviews; the prompts say these are for understanding only, and the review removes anything new.

**Earliest affected step:** the operator's first polish of a candidate paper.

**Calls per run:** +0 for the machine until the operator adopts a polish; then one review call (sometimes two) and one L9.

**Oscillation:** the check warns that `lean/ORCHESTRATOR.md`, `system/tools/polish.py` and `system/tools/README.md` remove text v14.7 and v14.8 added. Section 4h, v14.7's packet flow, is replaced on the operator's word by the operator-run polishes in the folder. v14.8's counting rule and limit are kept word for word in `polish.py`, and its clause in the opening paragraph is kept. The packet commands of `polish.py` go with the flow they served. The check also finds ORCHESTRATOR closer to v14.5 and v14.6 than to v15.0, because the packet section v14.7 added is replaced. That is not a return to the earlier versions, since 4h is rewritten, not removed. The paragraph v15.0 "added" is the opening paragraph, amended in place with v15.1's clause and v15.0's clause kept word for word.

**Size:** POLISH-STRUCTURE.md about 1,700 words; POLISH-LINE.md about +300 over POLISH-PROMPT.md; advisor.md about +620; ORCHESTRATOR about +150 net; polish.py about +120 lines net.

### Human review of paper-5's line polish (machine v15.1), 2026-10-24

**Kind:** a record, not a version. No machine file changed (nothing under `system/`, `spec/` or `lean/`). Added at the operator's request, so that the report on the competition work shows this step. The operator ran it in a claude.ai session (Claude, Opus) linked to the machine folder.

**What happened:**
- **The review.** the operator read a printout of `runs/paper-5/12_polish/… (line polish).pdf`, wrote margin notes, then gave a spoken pass through the paper. Claude checked every note against the competition's rules on human involvement, page by page. Each note was sent on in generic form, converted to generic form (the operator's wording or claim removed), refused (a substantive philosophical contribution), or left open (unreadable in the scan, or meaning unclear). About fifty items in all: one refused, four converted, seven left open and not passed, the rest sent.
- **A separate AI comprehension check.** the operator also ran a separate Claude conversation in which, by its own header, he asked only clarifying questions. Its eight suggestions are filed whole as `runs/paper-5/methodology/outside-reviewer-suggestions-2026-10-24.txt`. Claude evaluated each one and checked the algebra in four of them against the paper; it holds. That check found an error that had survived to the line polish: a sentence in §4 points at the wrong difference between the ordinary and the longtermist life (its R2(c)).
- **The operator's decisions:**
  - One combined line-and-structure revision, not a line pass alone.
  - Most of the spare words go to plain-language translations of the mathematics, modelled on the paper's own "Roughly, this is the condition…" sentence in §5.
  - The introduction's horizon paragraph stays in the main text.
  - §5 is kept and cut down substantially.
  - The D'Alessandro comparison at the end of §3 is condensed, and the discussion of Mogensen (2019) moves to a footnote.
  - Italics for terms of art at first use, and for "does" and "allows" in their technical senses.
- **The brief.** Claude wrote `runs/paper-5/12_polish/review-revision-brief.md` (about 3,500 words), which is everything the reviser gets:
  - every permitted item, in generic form, located by section and quoted passage;
  - the outside reviewer's file, to be read whole and treated as suggestions;
  - Claude's own comments, marked as from an AI;
  - which rules of `POLISH-LINE.md` still apply;
  - the order in which to spend the word budget;
  - a required response table covering every item.

  The prompt that opens the revision is `runs/paper-5/12_polish/review-revision-prompt.md`. Output stage name: `review revision`.
- **Keeping human wording out of the folder.** Every AI working in the folder can read every file in it. So the record of the review kept here, `runs/paper-5/methodology/human-review-log.md`, is redacted: the wording of the refused note, the converted notes and the unreadable notes is withheld. The operator keeps the full log outside the machine folder. A search of the run, `PAPERS/`, `REVIEW/` and `ADVICE/` found none of the withheld wording. `log.py human` recorded the step in `runs/paper-5/logs/interventions.md`.

**How `POLISH-LINE.md` is adapted for this revision (in the brief, not in the file):**
- **Still in force:**
  - rule A (change nothing the paper claims), except corrections accepted from an AI reviewer and steps an explanation must spell out, all listed in the notes;
  - names and titles only from the References or the bibliography;
  - quotations word for word (shortened only by ending early or by an ellipsis; no added italics unless marked);
  - citations kept with their claims;
  - anonymity;
  - the 6,000-word limit, footnotes included.
- **Relaxed:**
  - rule B, so glosses, examples, a summary paragraph, an introductory preview, signposts and footnotes may be added where asked for;
  - rule D on structure, so material may move between sections;
  - rule E on roadmaps, for the signposts asked for.
- **Title and abstract:** kept unless the revision makes the abstract inaccurate.
- **New citations:** only works in `02_corpus/bibliography.md` with the text held in `02_corpus/sources/`.

**What it shows about the machine:**
1. **The line polish did not translate the mathematics.** A careful human reader found the paper's mathematics correct but too often left without a plain statement of what it means. That was the reader's main request. Rules B and E of `POLISH-LINE.md` (no examples, no new content, no roadmaps) leave a line polisher little room to supply it.
2. **The introduction gave results before the argument.** It stated results before explaining the Paralysis Argument and why the long-term escape seems to work, which the paper only does in §2. The reader also could not work out several steps the paper reports without explaining them: why paralysis is a problem for the deontologist in particular, and why the escape's price is that every act must serve the far future.
3. **A second AI reading added real value.** A separate comprehension check, done by an AI with a human asking only questions, found an error and offered explanations of steps the reader had marked as unclear.
4. **Human records need keeping out of the folder.** Any human review whose record contains more than generic feedback must be redacted in the folder and kept whole outside it. The same holds for anything a human writes into the folder during a review.

**Predicted effect:** a paper a non-specialist philosopher can follow: the problem framed on page one, every key condition stated in words as well as symbols, and the contribution easy to find. Every move keeps its strength.

**Risks:**
1. **Length.** The added glosses could push the paper over 6,000 words; the brief sets priorities and names what to trim.
2. **Inflation.** Glosses could overstate what the formulas show. The brief keeps rule A and asks for every change of claim to be listed.
3. **Quotations.** Shortened quotations must be re-verified before submission.
4. **Adoption.** `polish.py adopt` would treat `review revision` as a line polish (`kind = "line"`, since the stage name lacks "structure"). The advisor's polish review, built for line-polish rules, would then remove the additions this revision was asked to make. How to adopt and verify the revision is the operator's decision before submission.

**Open:** save the transcript of the separate comprehension-check conversation next to its suggestions file, for provenance.

### Human review of paper-2-r2's structure polish (machine v15.1), 2026-10-25

**Kind:** a record, not a version. No machine file changed (nothing under `system/`, `spec/` or `lean/`). Added at the operator's request, so that the report on the competition work shows this step. The operator ran it in a claude.ai session (Claude, Opus) linked to the machine folder.

**What happened:**
- **The operator's choice.** Of the two polishes of `runs/paper-2-r2`, the operator chose the structure polish (5,098 words by `polish.py count`) as the text for the final revision. The line polish is kept for comparison.
- **The review.** the operator read a printout of `runs/paper-2-r2/12_polish/… (structure polish).pdf`, wrote margin notes, then gave a spoken pass. Claude checked every note against the competition's rules on human involvement, page by page. Each one goes to the reviser only in generic form, located by section and quoted passage: 75 items from the operator in all, nine of them conventions for the whole paper.
- **A separate AI reviewer.** A separate Claude conversation, run under the same rules, reviewed the structure polish against the line polish. By its header, the human chose the topic, selected the structure polish and asked only generic questions. Its ten suggestions (plus a list of checks already made) are filed whole as `runs/paper-2-r2/methodology/outside-reviewer-suggestions-2026-10-25.txt`. Claude checked every quotation the reviewer cites against the structure polish, and every comparison against the line polish, and they hold. All 46 quotations in the structure polish appear unaltered in the line polish. Claude accepted eight suggestions and modified two: one name for the verdict now reaches the abstract, and a new running example may be built rather than drawn only from the paper's material.
- **The operator's decisions:**
  - the structure polish is the text to revise, and its gains are kept (the question on p. 1, the survey of other views in §8, the line between persuasion and retraining in §4);
  - the title and abstract are not fixed;
  - italics for terms of art at first use, at the reviser's judgment;
  - two paragraph joins in §3;
  - two passages are preferred from the line polish;
  - the revision is to be run in Claude Opus 5.5 at extra-high effort, and the reviser is to show the operator the rendered paper in the sidebar as soon as it is saved.
- **The brief.** Claude wrote `runs/paper-2-r2/12_polish/review-revision-brief.md`, which is everything the reviser gets:
  - every permitted item, in generic form, organized by section, each with its passage quoted;
  - nine conventions for the whole paper (terms of art, referents, connectives, the disposition/verdict distinction, each section's function, one running case, the safety stake, situating Pettit, label reminders);
  - the outside reviewer's file, to be read whole, with Claude's judgment of each item;
  - Claude's own comments, marked as from an AI;
  - which rules of `POLISH-LINE.md` still apply;
  - the order in which to spend the word budget;
  - a required response table covering every item.

  The prompt that opens the revision is `runs/paper-2-r2/12_polish/review-revision-prompt.md`. Output stage name: `review revision`. The record of the review is `runs/paper-2-r2/methodology/human-review-log.md`, which gives the operator's notes only in generic form. `log.py human` recorded the step in `runs/paper-2-r2/logs/interventions.md`.

**How `POLISH-LINE.md` is adapted for this revision (in the brief, not in the file):**
- **Still in force:**
  - rule A (change nothing the paper claims), except corrections accepted from an AI reviewer and steps an explanation must spell out, all listed in the notes;
  - names and titles only from the References or the bibliography;
  - quotations word for word (shortened only by ending early or by an ellipsis; no added italics unless marked);
  - citations kept with their claims;
  - anonymity;
  - the limit: 6,000 words, counting everything except the References list (title, abstract, headings, body and footnotes), measured by the "Counted" figure of `polish.py count`.
- **Relaxed:**
  - rule B, so glosses, examples (one running case), reminders, section framing and a short characterization of Pettit's project may be added where asked for;
  - rule D on structure, so material may move, but the structure polish's order and gains stay;
  - rule D on the title and abstract, since neither is fixed;
  - rule E on roadmaps, for the framing asked for.
- **New citations:** only works in `02_corpus/bibliography.md` with the text held in `02_corpus/sources/`.

**What it shows about the machine:**
1. **The structure polish fixed order, not reference.** It moved the question to page one and gave persuasion its own section, but a careful human reader still lost his way most often at terms, labels and pronouns used as if already explained: "the interventions", "correction held in reserve", "the holder", "protected standing", "the threshold statute", the three regime names, "she" with no antecedent. Reordering made this worse in one place: §4 now uses terms that §§5–6 introduce.
2. **Compression hid the paper's own move.** In tightening the prose, the structure polish shortened the paper's one original step beyond what a reader could reconstruct, and dropped the gloss on "disposition to comply". The reader and the outside AI reviewer each marked both places independently.
3. **A key distinction went under two names.** The attitude the thesis turns on is called "her view of who should…" in the abstract and introduction and "her verdict on the oversight regime" from §2 on. Neither polish gave it a name early.
4. **Borrowed theory needs placing.** The paper relies on Pettit throughout without saying what his project is, so a newcomer could take republican political theory for part of the AI-safety literature, and "republicans" went unexplained.
5. **Illustrations come late and land well when they come.** The reader praised the one worked illustration (Pettit's passport case) and asked for examples at almost every abstract step. The paper's own cases appear only in §§5 and 7.
6. **Section functions fade after the introduction.** By §8, a reader no longer knew what a section was for, or what earlier material (Petersen's guarantees) it relied on.

**Predicted effect:** a paper a non-specialist philosopher can follow from start to finish: terms defined at first use and recalled when they return, one name for each attitude, Pettit placed, the added step explicit, a running case that carries the abstract steps, and the safety stake kept in view. Every move keeps its strength.

**Risks:**
1. **Length.** About 900 words of room against many requests; the brief sets priorities and names what to trim.
2. **Inflation.** A running case or a gloss could overstate what the paper shows, or settle what it leaves open. The brief keeps rule A and asks for every change of claim to be listed.
3. **Quotations.** Shortened quotations must be re-verified before submission.
4. **Adoption.** As with paper-5, `polish.py adopt` would treat `review revision` as a line polish, and the advisor's polish review, built for line-polish rules, would remove the additions this revision was asked to make. How to adopt and verify the revision is the operator's decision before submission.

**Open:** save the transcript of the separate AI reviewer's conversation next to its suggestions file, for provenance.

### Human review of paper-4's structure polish (machine v15.1), 2026-10-25

**Kind:** a record, not a version. No machine file changed (nothing under `system/`, `spec/` or `lean/`). Added at the operator's request, so that the report on the competition work shows this step. The operator ran it in a claude.ai session (Claude, Opus 5.5) linked to the machine folder.

**What happened:**
- **The operator's choice.** Of the two polishes of `runs/paper-4`, the operator chose the structure polish (5,189 words by `polish.py count`) as the text for the final revision. The line polish (5,507) was kept for comparison and for borrowing.
- **Two separate AI reviewers.** Two Claude conversations, run under the same rules, compared the polishes. By the file's header, the human asked only which lessons from paper-2-r2's revision carry over, and asked for the AI's suggestions. Their fourteen items, plus a list of checks already made, are merged in `runs/paper-4/methodology/outside-reviewer-suggestions-2026-10-25.txt`.
- **The check.** This session checked every quotation the reviewers cite against the polish it cites, and every comparison against the other polish, and recomputed every figure. They hold, with small slips in the descriptions:
  - one quoted phrase is the line polish's, not the structure polish's;
  - the paper's own lead-in, "Given the two symmetries", is treated as part of a quotation;
  - Draper's penalty is listed as part of Swinburne's measure;
  - "the question is on page 1" holds only through the title.
- **The judgments.** Claude accepted most items, modified six and declined one: a single illustrative theist carried through the paper, whose job a cheaper item does. Where the reviewers differed, it went with A on "exactly", with B on keeping the contribution statement unnumbered, and with B's cheaper illustration over A's running theist.
- **[A] items.** Claude added six items of its own. Two were found against the sources:
  - the paper called Draper's penalty a simplicity penalty, but in Draper (2016, 61) it belongs to his criterion of coherence, which the run's `work/source-check-2.md` already had right;
  - a sentence quoted from Mooney and Hendricks (591) reports Swinburne's argument, not theirs.

  The others: the structure polish gives Collins no first name at first mention; further wording slips; a figure's rounding; a sentence that misstated what the second case needs.
- **The operator's decisions:**
  - the structure polish is the text to revise;
  - no margin notes, so no human feedback on the paper's content;
  - this session, not a fresh run, applies the checked list and writes the revision, so no brief or opening prompt was written;
  - the revision is run in Claude Opus 5.5 at extra effort, and the rendered paper is shown to the operator in the sidebar.
- **The revision.** `runs/paper-4/12_polish/How Much More Probable Must God Be - The Evil-God Challenge and the Gap Problem (review revision).md`, with notes and a response table covering every item. It counts 5,927 by `polish.py count` and rendered at 12 pages, with a copy in `PAPERS/`. The record of the review is `runs/paper-4/methodology/human-review-log.md`. `log.py human` recorded the step in `runs/paper-4/logs/interventions.md`.

**How `POLISH-LINE.md` was adapted, as in paper-2-r2's brief:**
- **Still in force:**
  - rule A (change nothing the paper claims), except corrections accepted from an AI reviewer or found against the sources, and steps an explanation must spell out, all listed in the notes;
  - names and titles only from the References or the bibliography;
  - quotations word for word;
  - citations kept with their claims;
  - anonymity;
  - the limit: 6,000 words, counting everything except the References list (title, abstract, headings, body and footnotes), measured by the "Counted" figure of `polish.py count`.
- **Relaxed:**
  - rule B, for glosses, a two-sentence account of Swinburne's measure, plain-word statements of the mathematics, and signposts;
  - rule E, for the signposts asked for.
- **Not used:** the section order and headings were kept, and the title and abstract were left unchanged, since the abstract already used the names settled.
- **New citations:** one, Swinburne 2004, 53, checked against `02_corpus/sources/`.

**What it shows about the machine:**
1. **Each polish kept what the other lost.** The structure polish's order gains came at a cost: it dropped the line polish's glosses, its statement of the simplicity reply in the introduction, and its reason for the cap. Neither text alone was the best base. The chosen one needed about 150 words from the other.
2. **Compression introduced slips.** "The evidence lowers God", "right of", an undefined "the many", unclear referents, a first name lost. Each line-polish counterpart was correct.
3. **Labels multiplied.** The paper had two names for each challenge, five for the evil-god hypothesis and four descriptions of the symmetry premise, and "the bound" was coined in passing. Neither polish fixed them.
4. **The mathematics again lacked plain words.** The two-case argument and the cap's derivation needed the same translation paper-5's review asked for.
5. **The counter counts symbols.** Each letter in a formula is a counted word, so prose that explains a formula costs more than it looks. The first full draft counted 6,002 against an estimate of about 5,750. Budget for plain-word mathematics by running the counter, not by eye.
6. **Paraphrase drifts from the source after verification.** The run's own source check described Draper's penalty correctly, but the paper's wording had drifted to "simplicity penalty". Neither polish checks paraphrase against source.
7. **The AI reviewers' descriptions need checking too.** Their substance held, but several descriptions were slightly off. None would have harmed the paper if passed on unchecked.

**Predicted effect:** a paper a non-specialist philosopher can follow: each term glossed at first use, one name for each challenge, hypothesis and premise, the two cases and the cap stated in words as well as symbols, and the paper's own move about the simplest motives laid out step by step. Every move keeps its strength.

**Risks:**
1. **One reader, not two.** The session that judged the suggestions also wrote the revision, so no separate reader checked its judgments against the result. A fresh read before submission would catch what it missed.
2. **Room.** 73 words remain, so any later fix must be word-neutral or paid for by a cut.
3. **Quotations.** One new quotation was checked against the source. The revision should still be verified again before submission.
4. **Adoption.** As with paper-5 and paper-2-r2, `polish.py adopt` would treat `review revision` as a line polish, and the advisor's polish review, built for line-polish rules, would remove the additions. How to adopt and verify the revision is the operator's decision before submission.

**Open:** save the transcripts of the two AI reviewers' conversations next to their suggestions file, for provenance.
