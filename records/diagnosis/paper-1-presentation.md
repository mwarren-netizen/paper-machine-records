# Diagnosis: why paper-1 reads the way it does

**Date:** 2026-10-10. **Scope:** presentation only (not the strength of the arguments). **Method:** each complaint in the operator's feedback is traced back through the run's files to the step, role instruction, template or norm that produced it. File paths are relative to `runs/paper-1/` or to `system/`. The corrections in section 4 are proposals. Nothing in `system/` has been changed.

## Bottom line

1. **No one in the prose pipeline ever reads as a newcomer.** Every call that chooses, trims or judges prose (selector, section close, cut, V17 editor, V19 author) is first given the unit spec, the outline, the frozen project or the notebook. So each one already knows what "it" refers to, why the example is there and what every term means. The only cold readers in the run read the pitch (V10) and the front door (V18). The front door puts the abstract first, and the abstract supplies the context the opening withholds.
2. **Selection rewarded conformance to the spec, not readability.** The selector's stated test is "the one that does the unit's job best". The job, the moves and even some wording are fixed in the spec, and pass direction **a** is usually the spec's own order. The selector chose **a** in 23 of 39 units (one in three would be chance), including S1-U1 over a clearly better pass c.
3. **The norms are a checklist of what must be present, not an order of what the reader needs first.** Almost all of them are outline-level [O]. None says that a term must be introduced before it is used, that a pronoun needs an antecedent, that a technical result must be shown working, or that the problem must be in hand before the answer. Two norms were applied literally in ways that hurt: norm 1 became "the first sentence is a question", and norm 8 ("each section says its conclusion near its start") was applied to the introduction.
4. **Every length mechanism pushed toward compression, and none pushed back.** Units were small slots, avg. about 100 words with a ±10% tolerance. Closes trimmed, the V17 cut was told to "drop … examples", the wash may "compress", the LLM-pattern list penalises explanatory connectives, and V19 paid for each added hedge by cutting somewhere else.
5. **Freezes and dead channels kept known problems in place.** The selector flagged the missing antecedent. The flag was addressed to "the orchestrator" or "the editor", neither of whom ever reads flags. It became notebook liability 73 and stayed there. The frozen outline was later cited to reject both referees' requests to unload the introduction.

---

## 1. The opening sentence, traced

"How sure are you that it is wrong?" passed through six steps, and each could have removed it.

| Step | What happened | Where |
|---|---|---|
| V12 | Outline 1 uses "How sure are you that it is wrong?" as a working title. In a title, "it" works because the title is a label. | `06_outline/outline-1.md` |
| V14 | The frozen outline keeps that title and writes "frame the question (how sure are you that it is wrong …)" into the introduction's orders. | `06_outline/outline-frozen.md` l.15, l.93 |
| V15 | The S1-U1 spec fixes the wording: *"The question is stated in the words 'how sure are you that it is wrong', which is also the title's question."* Pass direction **a** is "open on the question put to the reader". The title label had become a sentence in prose. | `07_prose/sections/S1.md`, S1-U1 "Fixed" |
| V16 selection | The selector chooses **a**: "the question comes first in the title's own words". It rejects **c**, the best pass, by misreading norm 1: c opens on the tempting view ("To find out how sure you are about a moral question, ask what you would do. That is the standard advice of decision theory"), and the selector calls that "a claim about a literature before feeling the problem". It does notice the defect, but files it as *"Not substantive, for the orchestrator: the opening 'it' has no antecedent … kept because the fixed wording is the title's question; if the editor dislikes it…"* | `07_prose/units/S1-U1/selection.md` |
| V16 close | The close records the flag as liability 73 ("kept for the title's question") and leaves it. It also trims the second sentence into the "has leaked to the magazine you edit, describing …" construction, and turns "You think publishing would be wrong, but you may be mistaken" into "You think it would be wrong, but may be mistaken, and cannot say". | `07_prose/close-S1.md` l.42; `units/S1-U1/selected.before-close.md` vs `selected.md` |
| V17 | The title is replaced ("Moral Certitude Cannot Be Read Off Choice …"). The only reason for keeping the wording, the title echo, is now gone, and nothing checks what depended on it. The V17 editor reads the outline and the frozen project, so it knows what "it" means. It never sees flags.md or the liability list. | `07_prose/v17/selection.md`; V17 card |
| V18 | The desk-reject reader reads the abstract before the first page. The abstract says what the question is about, so the opening reads as "concrete". | `08_review/desk-reject.md` |

Pass c also fixes the larger problem the operator's feedback identifies. It opens by stating the view under examination: decision theory's advice that what you would choose shows how sure you are. That is the dialectical question. The case then tests it. Pass a opens on the case and never states the view.

**Mechanisms exposed:** (i) a spec-level "Fixed" item carried prose wording, and its reason (the title) could lapse without anyone noticing; (ii) the selector judged against the spec; (iii) norm 1 is ambiguous between "make the reader feel the problem" and "open with a question"; (iv) flags addressed to the editor had no route to the editor; (v) every reader who could have caught it already had the context.

---

## 2. Each complaint, traced

### 2.1 "The reader is given the answer before being taught to recognise the question" (dialectical situation not established)

- **Norm 8 applied to the introduction.** The outline template asks every section, including S1, for "Conclusion it states near its start". Outline 1 answered: "By its second paragraph: choice cannot tell how sure someone is from how much she cares about doing right." So the thesis had to come before Smith's challenge was explained. Paragraph (c), the thesis, comes before paragraph (d), the debate. (`system/templates/outline.md` l.33; `06_outline/outline-1.md` l.48)
- **Norms 1 to 5 read as a list of contents, not a sequence.** Norm 1 (question before thesis) was met with a case-question. The *dialectical* question (why moral certitude is a problem for expressivists) is covered only by norm 4 ("say which debate the paper enters"). The outline treated that as a placement item and gave it about 130 words. In the spec it became S1-U5, with 65 words for Smith's challenge "in one sentence an outsider can follow". The V11 judge's advice had said the same: "introduce Smith's challenge in one sentence for an outsider".
- **Norm 2 plus the V13 editor front-loaded the answer further.** E9 imported the positive account's verdicts into the introduction ("give the reader the conclusion in some detail (norm 2)"). So the introduction delivers the thesis, the central move, three verdicts of the positive account, *restricted parity* and a roadmap, all in 630 words and all before the reader knows what Smith's challenge is. (`06_outline/v13-editor.md` E9; `v14-response.md`)
- **Three entry strategies stacked in one introduction.** The outline used Diagnosis as the frame, the Puzzle as the opening device, and a case on top of both. Each strategy brings its own obligations. (`outline-1.md` l.8, l.21)

### 2.2 "Compresses arguments into declarations" (state-dependent utility)

- **The spec required a clause.** S2-U3 "Fixed": *"The state-dependent utility result gets a clause and a footnote."* Its budget was 100 words for four moves. (`sections/S2.md`)
- **The selector again chose the spec's order.** Pass b began with a worked case: a bet on rain pays in money, worth the same wet or dry; an umbrella prize is worth more when it rains. The selector chose a, the two-sentence declarative version, and kept only a fragment of b's example.
- **The source was never opened.** The result was known only through "fetch summaries", so no writer could explain it from the text. The concrete illustration the operator's feedback supplies (80% credence with low concern against 40% with double concern) is exactly the kind of worked example the spec did not ask for. No norm asks for one when a technical result is invoked.

### 2.3 "Syntactically economical to the point of opacity" ("The trouble reaches any cognitivist or expressivist who identifies credence with choice")

- **This sentence is in the abstract, which the V17 and V19 rules hold to 150 words.** Abstract compression is the extreme case of a pattern that runs through the whole text.
- **Compression is rewarded at every stage and penalised at none.**
  - The selector's wash: "you may compress, smooth … remove filler" (`roles/author-selector.md`).
  - Closes shortened 25 of the 34 units they rewrote, by 2 to 32 words each (e.g., S2-U5 247→215, S3-U8 147→121), even where the section was within its margin.
  - The V17 cut removed orienting sentences such as "The rest of this section says why" and the Paul example (`07_prose/paper-v1-cut-record.md`).
  - The LLM-pattern list penalises "This matters because", colon reveals and "a moral at the end", which are the connectives that make logical structure explicit. It has no entry for over-compression.
- **The V17 editor counted the result,** "the clipped verdict" in 15 of 52 paragraphs, but read it as rhythm, not as missing steps.

### 2.4 Technical vocabulary before the reader knows what work it does

- **Norm 14 and the author's glossary make naming a duty.** "Central theses get informative names"; the author keeps a "glossary of named theses" and must "use the glossary's names in every outline and every unit". The frozen glossary has about 15 entries, and the V17 editor counted about 16 terms of art in 3,800 words. The LLM-pattern list warns against "label proliferation", but only as a frequency test applied to a list that the glossary rule fills.
- **The unit spec has no field for the reader.** The template asks for *Job, Moves, Handoff, Budget, Fixed, Open, Pass directions, Sources*. There is no field for "what the reader must already have" or "terms introduced here, and how". So definitions arrive as moves (S3's lean, outlast, erase, margin), with the example after the definitions. The V17 editor asked for "example first", but by then any change had to be word-neutral.

### 2.5 The paper does not distinguish its two projects

- **The shape template invites a second thesis.** The word-budget's "one central argument and two or three pressure points at roughly 1,000 words each" is restated in the pitch mode. Nothing says that a pressure point must press on the central argument, so the positive account (S3) and its defence (S4) filled the two pressure-point slots, about 1,740 words against about 1,100 for the negative argument.
- **The V11 judge's architectural advice was lost at V13.** The judge wrote "Make the concern channel the paper, and give it the most space … Keep the positive account short." The V13 editor's reading list does not include `04_judge/v11-choice.md`, so the editor chose outline 1 without that advice.
- **Ownership kept the original view.** P2's author began as voice B, whose starting view was the positive one (certitude as exposure to revision). The author role says advice is "not binding" and the frozen project "is fixed", so the author defended both halves.
- **By V17 the split could only be named, not fixed.** The editor saw it ("The fist is split … V13 accepted this architecture and I do not reopen it"). At V19 the author cited the frozen outline to reject a referee's restructuring request (U-R9).

### 2.6 Qualifications interrupt the argument

- **The writer's knowledge is saturated with objections.** Every pass writer reads the author's notebook first: 21,472 words, about four times the paper's length, with roughly 95 numbered liabilities from V05, V09, V12, the V13 editor and every close. The prose is written to answer that file of critics, not to orient a first reader.
- **V19 turned referee pressure into more hedges.** The response accepted U-R3, U-R4, U-R5, U-R6 and U-R7, each adding a qualifying sentence ("maximum 45 words", "maximum 12 words" and so on). Because revision is word-neutral, those were paid for by cutting elsewhere. The net effect was more boundary-drawing per word.
- **No norm puts the mechanism before its boundaries.** The spec for S1 put "restricted parity" (the scope limit) in U6 of the introduction, before the mechanism it limits had been shown working anywhere.

### 2.7 A familiar insight presented as an unfamiliar one (underdetermination; Davidson; state-dependent utility)

*Lower confidence.* the operator's taste file (read by the judge) dislikes novelty that "consists mainly in 'applying X to Y'". The V11 judge treated "an instance of a known non-identification result" as a risk to the paper's novelty. The author's response kept "novelty over state-dependent utility not claimed" as a limitation. Nothing in the norms says to use a familiar structure to explain the new point; the pressure is all toward distance from it. The decisive source (Schervish, Seidenfeld and Kadane) was never opened, which made leaning on it impossible anyway.

### 2.8 "Optimised for defensibility at the expense of intelligibility"

That is an accurate description of the machine's checkpoint structure:

| Kind of check | Where it runs |
|---|---|
| **Adversarial** (is it defensible?) | V05 critics, V09 challenge, V12 outline-check, V13 and V17 editors, V18 unsympathetic referee, plus a liability ledger that grows at every step |
| **Intelligibility** (can a newcomer follow it?) | V10 cold readers (pitch only); V18 desk-reject (front door, abstract first, asked whether to send out, not where it stalled); referee question 6 (answered, then rejected under the freeze or the word limit) |

Defensibility has many checkpoints, all with authority to change the text. Intelligibility has no checkpoint with authority at all.

---

## 3. Five root causes

1. **Knowledge contamination of every prose judge.** A judge who has read the spec cannot see what the spec supplies. This explains the antecedent, the unexplained technical results and the jargon, and why the selector believed S1-U5 could be "followed by an outsider". LLM readers make it worse, because they reconstruct missing context fluently unless they are made to log every reconstruction.
2. **The spec is a second author, and selection obeys it.** "Fixed" items carry wording and order. Direction a is the spec's default. The selector's criterion is "the job" as the spec defines it. So the three-pass design gives less variety than it appears to, and readability is never what is being selected for.
3. **The norms specify contents, not reader order.** Nothing governs given-before-new, term before use, problem before answer, or mechanism before boundary. Norms written for outlines were applied to prose, and in two cases (norms 1 and 8) were read literally.
4. **Asymmetric length pressure.** Every tool removes words; none protects the words that do explanatory work. The budget's slot grain (39 units, about 100 words each) is finer than the grain at which explanation happens. A reader often needs an extra 40 words *here*, paid from *there*, and the system can only do that at a section close, where the instruction is to trim.
5. **Freezes protect exposition as well as identity, and flags have no reader.** The freeze was meant to protect the claim and the spine. In practice it also protected the order and proportions of exposition. Flags addressed to the editor and presentation liabilities had no consumer. A fixed constraint whose reason lapsed (the title echo) was never revisited.

---

## 4. Proposed corrections

Each item gives the change, why it generalises beyond this paper, and the risk it creates, with a guard. They are in order of expected effect. C1 to C3 address root causes 1 to 3 directly. Norm amendments are the operator's to approve.

### C1. A newcomer read with authority, in the prose stages (root cause 1)

- **Change:** add a fresh "first reader" call that reads **only the prose**: no spec, outline, notebook or abstract. It runs at two points:
  1. after each section close, reading the draft up to that point;
  2. at V17, on the assembled body before the cut and the editor.

  It follows a *stall-log protocol*. Sentence by sentence, it records every place where it had to guess: a referent not yet given, a term used before it is glossed, a step asserted rather than shown, "why is this here?", "what is the question this answers?". It reports stalls, not rewrites. The close (or the V17 author) must answer each stall: fix it, or reject it with a reason, as for referee recommendations.
- **Why it generalises:** comprehension failures are content-independent. The read carries no philosophical view, so it cannot bias the argument.
- **Risks and guards:**
  - *Over-explanation and length creep.* Guard: stalls are logged, not remedies prescribed, and the author pays for fixes within the section budget.
  - *Model readers reconstruct too well.* Guard: the protocol makes the reader write what it needed and where it found it. Calibrate on known cases: it must flag paper-1's opening and the S3 definitions, and should flag little in a good published introduction.
- **Cost:** about 5 + 1 calls per run.

### C2. Reader-first selection; spec conformance second (root cause 2)

- **Change, in four parts:**
  - **Selector order.** The selector reads the draft and the three passes *before* the spec, ranks them for a first reader, then opens the spec only to check that the job is done, the claims are within scope and the glossary terms are right. Rewrite its criterion to: "the pass a first reader of the draft so far would follow best, provided it does the unit's job".
  - **Shuffle labels.** The orchestrator shuffles which direction is labelled a, b, c, removing the position bias that the 23/39 count suggests.
  - **Narrow "Fixed".** In V15, "Fixed" may hold commitments (claims, scope, terms, examples, quotations), not wording or sentence order. Any fixed wording must carry its reason, so that it lapses when the reason does.
  - **Escalate the right flags.** A selector flag about readability is "substantive" whenever it would stall a first reader. Such flags go to the close as must-answer items, not to "the orchestrator".
- **Why it generalises:** it changes what selection optimises, not what the paper says.
- **Risk:** the selector may drift from the spec's argumentative job. Guard: the job check stays a hard condition, and only *among passes that do the job* does readability decide.

### C3. A few prose-order norms (amendments for the operator) and a balanced pattern list (root cause 3)

- **Proposed [P] norms:**
  - (a) **Given before new.** Nothing is referred to before it is introduced: no pronoun without an antecedent, no term before its gloss or its example.
  - (b) **Problem before answer.** The reader has the dialectical problem (the view under examination and why it is hard) before the thesis that answers it. A case may motivate the problem but does not replace stating it.
  - (c) **Show a technical result once.** A result from another field that the argument relies on is shown working on the running example, not only named.
  - (d) **Mechanism before boundary.** The central move is shown working before its scope is restricted, and restrictions are gathered in one place.
- **Clarifications to existing norms:**
  - *Norm 1* means "the reader feels the problem", not "open with a question".
  - *Norm 8* applies to body sections. The introduction is governed by norm 2 (thesis by the end of the introduction).
  - *Norm 2's* "conclusion in some detail" does not import a secondary thesis's verdicts into the introduction.
- **Pattern list:**
  - Add *compression tells*: chains of dropped subjects, abstract nouns as agents ("the trouble reaches"), terms of art before their gloss, results named but not shown, paragraphs that end on a clipped verdict.
  - Add to the wash rule: compress only where no step a reader needs is removed.
- **Why it generalises:** these are genre norms for philosophy prose (they are in Mehta and Huemer, whom the norms already cite), not features of this paper.
- **Risk:** more norms is more for the model to juggle. Guard: four short norms, each checkable on a sentence, and they replace ambiguity in norms 1 and 8 rather than adding new obligations.

### C4. Length mechanics that protect explanation (root cause 4)

- **Unit tolerance.** Widen it to ±25%, with the section total as the hard constraint. The close balances within the section.
- **Track notes from the start.** Measure footnotes against the notes reserve from the first V16 unit, not only at V17. This run drafted 1,690 words of notes against 900 and the cut took 170 words of body to pay for it.
- **Cut priority.** In order: apparatus and redundant citations, repeated statements beyond norm 12's licence, secondary objections and hedges, then anything else. Examples and orienting sentences go last. Never cut a sentence whose removal leaves a later one uninterpretable. Replace "drop the least necessary qualifications and examples" in the author's `cut` mode.
- **V19 additions.** Additions that only defend (limits, qualifications, replies to non-central objections) go to footnotes by default unless they bear on the central claim. Additions that clarify have priority over defences when words are short.
- **Why it generalises:** these are budget rules, independent of content.
- **Risk:** a looser unit tolerance can let one unit balloon. Guard: the section total still binds, and the close sees the counts.

### C5. Scope the freeze, carry architectural advice forward, declare primary and secondary contributions (root cause 5)

- **Freeze scope.** In the author role and the V17 card: the freeze covers the claim, the spine and the section jobs. The *order of exposition within a section* and the *proportions between sections, within ±15%*, may change at V17 or V19 when a reader report (C1, a referee's question 6 or the editor) shows a reader could not follow. Citing the frozen outline is not a sufficient reason to reject a readability recommendation.
- **V13 reads the V11 choice.** Add `04_judge/v11-choice.md` to V13's reading list, and ask the editor to check proportions against the judge's advice.
- **Declare contributions.** Add to the outline template: "Primary contribution; secondary contribution (if any) and how it depends on the primary." The introduction must say which is primary. In word-budget.md, redefine a pressure point as something that presses on, applies or extends the central argument; a second thesis must be declared as such.
- **Why it generalises:** structure-level rules.
- **Risk:** loosening the freeze invites late churn. Guard: the claim and the spine stay frozen, and only reader-evidenced changes to exposition are allowed.

### C6. Give flags and liabilities a reader (root cause 5)

- **Presentation flags to the editor.** Unresolved presentation flags and liabilities (a type to add to the liability ledger) go into the V17 editor's and the V19 author's reading lists.
- **Re-check lapsed reasons.** When V17 replaces the working title, the author re-checks the fixed items whose stated reason was the title.
- **Why it generalises:** plumbing.
- **Risk:** none of note.

### C7. Lower-confidence changes (test before adopting)

- **A writer's brief.** For V16 passes, an extract of the notebook (claim, glossary, the liabilities that bear on this unit) instead of the whole notebook, with the instruction to "write for a reader who has not seen the notebook". *Risk:* loss of continuity. Test on two sections first.
- **A familiarity norm.** "Where the central move is an instance of a known structure, say so early and use it to explain; the novelty is what the instance shows." *Risk:* tension with the operator's taste about "applying X to Y". The operator should decide whether that taste is about contribution (keep) or exposition (relax).

### Choices that were the operator's, flagged for review, not as errors

- **The word budget.** The conservative budget (5,000 target, everything counted against a 6,000 limit whose counting rules are unstated) left a body of about 3,800 words for two projects plus a heavy apparatus.
- **The citation roster.** The early-footnote norm (cite every party and every likely referee) cost about 120 words in the first note and contributed to a reference list of 545 to 644 words.

Both are defensible trade-offs, and both took words from explanation.

---

## 5. How to test the corrections before the next run

Paper-1 is a ready-made regression set:

1. **Re-run selection** on S1-U1, S2-U3 and three S3 units with the revised selector (C2) and shuffled labels. Expect c for S1-U1 and b for S2-U3, or a stated reason otherwise.
2. **Run the newcomer read** (C1) on `07_prose/paper-v1.md`. It must flag the opening antecedent, Smith's challenge in S1-U5, the state-dependent utility sentence and the S3 definitions. As a negative control, run it on the introduction of a published exemplar (e.g., Street's "A Darwinian Dilemma"), where it should stall rarely.
3. **Re-expand S1** under the amended norms (C3) and outline template (C5) and check that the dialectical problem precedes the thesis.

These need only a handful of calls and would show whether the corrections fix the observed failures without obvious new ones.

---

## 6. What the orchestrator contributed

- From the S2 close on, the orchestrator added to each close's task line the fact that footnotes were over the reserve. That is accurate, but it adds pressure to trim.
- The orchestrator's reading-list helper missed sources for some units: S3-U2 was rerun after a miss, logged as a deviation. That added noise rather than causing these failures.
- Under ORCHESTRATOR rule 7 the orchestrator does not read flag files. So the selector's "for the orchestrator" flag reached no one. That is a design gap (C6), not a judgement call, but it was in the orchestrator's lane.

## Appendix: evidence

| Item | File |
|---|---|
| Opening passes and the selection | `07_prose/units/S1-U1/` (pass-a/b/c, selection.md, selected.before-close.md, selected.md) |
| Spec "Fixed" for S1-U1 and S2-U3 | `07_prose/sections/S1.md`, `S2.md` |
| Selection counts | `grep '^chosen:' 07_prose/units/*/selection.md` (a 23, b 7, c 9) |
| Liability 73 and the dead flag | `07_prose/flags.md` l.10; `07_prose/close-S1.md` l.42 |
| Thesis in paragraph 2 | `06_outline/outline-1.md` l.48; `system/templates/outline.md` l.33 |
| Verdicts imported into the introduction | `06_outline/v13-editor.md` E9 |
| Judge's proportion advice | `04_judge/v11-choice.md`, "Advice for the winner's outline" |
| Cut removing examples and signposts | `07_prose/paper-v1-cut-record.md`; author role, mode `cut` |
| Editor's notes | `07_prose/v17/editor-notes.md` |
| Freeze cited against readability | `08_review/response.md`, rows S-R2, U-R9, U-R10 |
| Notebook size | `05_papers/P2/notebook.md` (21,472 words) |
