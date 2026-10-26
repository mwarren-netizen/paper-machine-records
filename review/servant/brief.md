# Revision brief: paper-2-r2, review revision

**Paper:** "Who May Correct a Willing Servant? Corrigible Persons and Domination"
**Run:** `runs/paper-2-r2`
**Text to revise:** the structure polish, `runs/paper-2-r2/12_polish/Who May Correct a Willing Servant - Corrigible Persons and Domination (structure polish).md`. The operator chose it over the line polish. The line polish, in the same folder as "(line polish).md", is for comparison and for the passages this brief tells you to take from it.
**Output stage name:** `review revision`
**Prepared:** 2026-10-25
**To be run in:** Claude Opus 5.5, extra-high effort (the operator's choice)

---

## 1. What this task is

The operator, who runs the machine, read a printout of the structure polish and wrote margin notes, then added a spoken pass. A separate AI reviewer also read it. This brief collects all of their feedback, in generic form. Your job is to write one revised version of the paper that answers it.

The revision combines line-level and structural work. It may:

- add explanations, glosses, reminders and examples;
- move material between sections;
- condense or cut passages that aren't pulling their weight;
- revise the title and abstract (neither is fixed).

There is a lot of feedback here, and all of it is meant to be acted on. Work through every item. You may decline an item, but only for a reason, and you must record what you did with each one (section 8).

**Keep the structure polish's gains.** The structure polish already fixed three problems in the line polish, and the revision must not undo them:

- the question now comes on p. 1, not after five authors;
- the survey of other views has moved to its own section, §8 "What the Argument Adds", so the introduction runs from Petersen to the question to the thesis;
- the line between persuasion and retraining has its own section, §4, right after §3, so the "proves too much" worry is answered when it arises.

(These are the outside reviewer's item 0, checked against both texts for this brief.)

## 2. The rule you are working under

The paper is an entry in a competition that requires the essay's substantive philosophical content to come from AI.

- **A human may** point out that something is unclear, underdeveloped, repetitive or out of order, ask for an example or a rewrite, give generic method instructions, set length, style and structure constraints, choose among AI outputs, and ask for material to be cut.
- **A human may not** supply arguments, premises, distinctions, objections, replies, examples, qualifications or wording.

So:

- **The human's notes are generic on purpose.** They say where a careful reader got lost and what kind of fix is wanted. They never tell you what the fix is. Work the solution out yourself, from the paper, its sources (`runs/paper-2-r2/02_corpus/`) and its plan (`runs/paper-2-r2/work/plan.md`).
- **Don't add a claim on a note's authority.** If a human note seems to point toward a particular philosophical claim, decide on the merits, as you would for any change.
- **The AI reviewers' suggestions are AI-originated.** You may use them, but they are suggestions, not instructions. Accept, modify or reject each one on its merits, and say which.
- **Don't look for other human input on this paper.** The record of the review is `runs/paper-2-r2/methodology/human-review-log.md`. It adds nothing to this brief, and you don't need to read it.

## 3. Sources of feedback

- **[M] Human reader (the operator).** Margin notes on a printout of the structure polish, plus a spoken pass. They are given here in generic form, with IDs matching the review log (M-1.1, M-G1, …). Page numbers refer to the rendered structure polish (`12_polish/… (structure polish).pdf`). Every note also quotes the passage it concerns. **A cluster of question marks in the operator's notes always means "this needs to be clearer".**
- **[R] Outside AI reviewer.** `runs/paper-2-r2/methodology/outside-reviewer-suggestions-2026-10-25.txt`. **Read it in full.** It is cited here by item (R1, R5, …). Every quotation it cites was checked against the structure polish, and every comparison against the line polish. All of them hold. How each item was judged is in section 7.
- **[A] Second AI reviewer.** Comments from the Claude session that prepared this brief. They are marked [A] and collected in section 7.

## 4. Which rules from `POLISH-LINE.md` still apply

Read `POLISH-LINE.md`. Its guiding principle, **cognitive empathy with the reader**, applies in full: it is the point of this revision. The operator's central complaint is that the paper often uses terms, labels and pronouns as if the reader already knew what they meant. Read as the intelligent newcomer `POLISH-LINE.md` describes.

Its hard constraints apply as follows.

**Still in force:**

- **A (change nothing the paper claims).** Every move keeps its strength and its qualifications. There are two exceptions:
  - where you accept an AI reviewer's correction;
  - where a requested explanation needs you to state a step the paper leaves implicit.

  List every such change in your notes. Examples and glosses must claim no more than the paper argues.
- **C (names and titles only from the References list or `02_corpus/bibliography.md`).**
- **D, quotations and citations:**
  - Every direct quotation stays word for word, with its citation attached.
  - You may shorten a quotation only by ending it earlier, or by marking an omission with an ellipsis. Never alter its words.
  - Don't add italics inside a quotation unless you mark "emphasis added".
  - Page references stay attached to the same claims.
  - Markdown conventions stay as they are.
- **Anonymity.** Add nothing that identifies the author.
- **F, length.** **The limit is 6,000 words, counting everything except the References list: title, abstract, headings, body and footnotes.** Measure with `python3 system/tools/polish.py count "<file>"` and use its "Counted" figure. The "machine's all-in count" it also prints includes the References and is NOT the limit. The structure polish counts 5,098, which leaves about 900 words of room. Moving text to a footnote saves no words.

**Relaxed for this revision:**

- **B (add no new content).** Where the feedback asks for them, you may add:
  - glosses and definitions of terms of art;
  - examples, including one running case (M-G7);
  - reminders of labels and earlier results;
  - section framing and signposts;
  - a short characterization of Pettit's project;
  - transitions that make logical connections explicit.

  You may also add a sentence an AI reviewer suggests, if you accept it.
- **New citations.** Only for a work that is already in `02_corpus/bibliography.md` and whose text is held in `02_corpus/sources/`. Check every quotation and page reference against the source. If you can't check it, leave it out.
- **D, structure.** You may move material between sections and paragraphs. Keep the structure polish's section order and its three gains (section 1). Change a heading only if a move makes it inaccurate, and say so in your notes.
- **D, title and abstract.** Neither is fixed. Revise the abstract to match the revision, in particular the terminology settled under R2 and M-A1. The abstract counts toward the limit, so keep it about as long as it is now.
- **E (no roadmaps).** Signposting that the feedback asks for is allowed: telling the reader what a section is for (M-G6), the framing of §8 (M-9.5, R9), and the reminders (R7). Everything else in E still applies: no throat-clearing, no filler, no closing sentences that restate the paragraph.

## 5. Priorities and word budget

About 900 words of room sounds generous, but the feedback asks for a great deal. Spend words in this order:

1. **Terms, labels and referents (the reader-empathy pass).** This is the top priority:
   - glosses at first use (M-G2, M-1.3, M-2.6, M-3.7 and others);
   - one name for the verdict, and a sharp disposition/verdict distinction (R1, R2, M-G5);
   - reminders when a label returns (R7);
   - clear pronouns (M-G3).

   Most of these are a few words each, and together they do the most for the reader.
2. **Examples and one running case** (M-G7, M-2.1, M-4.3, M-4.5, M-4.7, M-7.1, R8). This is the biggest single expense, so keep the running case compact. Introduce it once, briefly, and afterwards refer back to it in a clause, not a paragraph.
3. **Explanations of steps a reader couldn't follow:**
   - the paper's added step (R5, M-4.5);
   - the qualifications on the second part, plain version first (R4);
   - the impairment exception (M-2.3);
   - the unsupported claims (M-3.9, M-6.7).
4. **Framing:**
   - situating Pettit (M-G9);
   - whose view is the target (R10, M-A1);
   - each section's job (M-G6);
   - §8's bridge (R9, M-9.5);
   - keeping the safety side visible (M-G8).
5. **Expanding §5's three regimes** (M-7.1).

**Make room by:**

- removing the sentence the operator marked as bad writing (M-4.1);
- cutting the passages that only repeat a point already made (M-7.8 asks you to check one);
- dropping or shortening the Soares "impostors" sentence if it isn't needed (M-6.5);
- shortening the repeated full statements of the second part of the thesis. Once R4's plain version is in place, later restatements can lean on it, but every qualification must survive somewhere in each place the thesis is stated in full;
- tightening §8's survey without dropping any author or quotation's role;
- cutting anything else that isn't pulling its weight.

Don't drop a move, a qualification or a quotation the argument relies on.

## 6. The feedback, section by section

### Conventions for the whole paper

- **M-G1, italics for terms of art.** Italicize a new term or phrase the paper relies on, at the point where it is introduced or defined, so the reader stays alert to it. Use judgment: the first introduction only, not every recurrence, and never inside a quotation unless marked "emphasis added". Candidates include *corrigible*, the disposition to comply, the verdict on the oversight regime, *protective rule*, *threshold statute*, and the three regime names in §5 (M-7.1).
- **M-G2, terms used as if already established.** This is a common problem in the paper: it refers to terms as if they had already been set up in the flow of the paper when they haven't. Go through the paper asking, at every special term or idiom, whether a newcomer would know:
  - that it is being used in a special way;
  - what it means;
  - whether its definition needs a reminder here.

  Explain at first use; remind where it returns after a gap (see R7). The operator names, among others, "the interventions", "correction held in reserve", "alignment", "independent protection", "a standing one", "the holder", "protected standing", "republicans", "other side", "the ground", "threshold statute" and the three regime names. Treat these as examples, not a complete list. Put yourself in the reader's place and find where else they might get lost.
- **M-G3, referents.** Many uses of "it" are unclear; "this" often does better. Make clear who "she" and "her" are when she enters a passage. Throughout, she is the artificial servant, but passages sometimes start talking about her without saying so. Check "they" as well. Specific places are listed below.
- **M-G4, connectives.** Make the logical connections explicit:
  - Don't use "and" where a clause corrects, qualifies or stands in tension with the rest of the sentence; use "but".
  - Where one claim gives the reason for another, or follows from it, say so ("that is why", "it follows that" and the like).
- **M-G5, attitudes, dispositions and verdicts.** A lot of the paper's work is done by the distinction between her disposition to comply and her verdict on the oversight regime, and by talk of her "attitudes". Make these distinctions as clear as possible, and keep the terms fixed once set. (Related: R1, R2.)
- **M-G6, what each section is for.** The introduction frames itself, but it gets less and less obvious what each later section is trying to accomplish. Before revising, take a moment to ask, for each section and without adding anything, what it is attempting to accomplish, and whether that function is clear to the reader, implicitly or explicitly. Where it isn't, make it clear. This matters most for §8 (M-9.5).
- **M-G7, a running case.** Consider one concrete case that runs through the paper, realistic and easy for the reader to imagine. Introduce it early, and return to it judiciously wherever an idea needs illustrating, especially where an idea moves to the AI case. The point is to let the reader track which modifications to the case do or don't meet the paper's conditions as the argument proceeds. Use it only where it helps; this is not a requirement for every point. You build the case yourself. (See R8 and [A] in section 7.)
- **M-G8, keep the safety side visible.** The paper is not only about the permissible correction of artificial persons. Its question is whether corrigibility reconciles *safety* and welfare. Where it matters, remind the reader that the question of permissible correction has to be set against the question of AI safety. The operator singles out the introduction's paragraph beginning "The question matters because correction is a central tool of AI safety" as very good, for exactly this reason. The safety half is underdeveloped compared with the servant's protection, especially in the conclusion (M-10.3).
- **M-G9, situate Pettit.** As it stands, a reader might take Pettit's work to belong to the AI-control literature. Say briefly what Pettit's project is and what it is trying to accomplish, and that the paper applies it to artificial persons. Readers will want to track which considerations come from political philosophy and how they are being applied here. Do this where Pettit is first relied on (M-3.6). That is also the place to say what "republican" means in his sense (M-6.2). Where an illustration taken from Pettit or from human cases is carried over to the AI case, make clear how it carries over.
- **R7, remind readers of labels.** Where a label comes back after a gap, remind the reader in a few words what it refers to. The outside reviewer lists "the first condition", "the protective rule", "the threshold statute", "supported agency" and "discretionary paternalism".

### Title and abstract

- **M-A1.** *"Long, Sebo and Sims report the suggestion that artificial persons built to share our values would not need to be disenfranchised."* The opening needs work. "Report the suggestion" is awkward, and it isn't clear whether the paper argues against the reported view or develops it further. Make the target and the paper's stance toward it clear. Keep Long, Sebo and Sims as the named source of the view.
- **R2.** The abstract calls the verdict "her view of who should correct systems like her". Bring it into line with the single name settled under R2 (section 7).

### §1 Introduction (pp. 1–2)

- **M-1.1.** *"Can continuing power over a servant's values subordinate her even when she endorses the interventions?"* Which interventions? "The interventions" is used as if already introduced.
- **M-1.2.** *"A corrigible system, in the safety literature's sense…"* Italicize at first use (M-G1).
- **M-1.3.** *"I argue that, for a servant who can judge how she should be governed, correction held in reserve cannot deliver this reconciliation."* "Correction held in reserve" is too dense. The reader needs to understand the nature of that correction and the nature of the reserve. The same applies to "keeps that power in reserve" on p. 2 (M-2.7).
- **M-1.4.** *"The question matters because correction is a central tool of AI safety…"* Keep this paragraph; the operator finds it very good (see M-G8). The line polish gives it the same text, set as its own paragraph after the question. You may adopt that paragraphing.
- **R10.** At the point the thesis is stated, a newcomer should know what view is being argued against and why it matters. At present, Long, Sebo and Sims's suggestion and the statement of the target ("My target is any version of the reconciliation that keeps that power in reserve") come after the thesis. (Related: M-A1.)
- **M-2.1.** *"…because the match between her will and the power's exercise depends on the holder's will and not on hers."* An example would flesh this out. (See M-G7, R8.)
- **M-2.2.** *"Second, independent protection can leave her undominated."* "Independent protection" appears without explanation. Make clear what it is, at least roughly, at first use.
- **R4.** *"…it can do so only under a rule that forbids anyone, at discretion or by law, to retrain her view of who should hold the power to correct systems like her, on any initiative but her own, except on a finding that her capacity for judgment is significantly impaired."* State the core claim plainly first, then add the qualifications one at a time, each with a word on why it is there. Don't drop or weaken any qualification. The chain recurs in §6 and the conclusion.
- **M-2.3.** *"…except on a finding that her capacity for judgment is significantly impaired. If her disposition to comply can be changed without changing that view, which I assume, such a regime may enforce oversight and may restore the disposition."* A careful reader couldn't tell what the impairment exception covers. Does it concern her view, her disposition to comply, or both? And how does it relate to restoring the disposition? Make clear what the paper claims, here and wherever the exception returns (§6, conclusion).
- **R1.** *"If her disposition to comply can be changed…"* Gloss "disposition to comply" at first use. The line polish's gloss is available.
- **M-2.0.** At the end of the second part of the thesis (*"We must deliberate with her and sometimes lose, or disenfranchise her."*): would an example help illustrate the idea? (See M-G7.)
- **R2.** *"her view of who should hold the power to correct systems like her"* and *"her view of who should govern correction"*. These are the same attitude as "her verdict on the oversight regime" from §2 on. Settle one name, introduce the distinction early, and use the name consistently.
- **M-2.4.** *"Long, Sebo and Sims report a strong form of the hope…"* and *"They report the suggestion without endorsing it…"*. "Report… the hope" and the repeated "report" are awkward.
- **M-2.5.** *"They report the suggestion without endorsing it, and go straight on to Schwitzgebel and Garza's objection to creating such systems. Nor do they rest it on correction."* These sentences are not clear, particularly "Nor do they rest it on correction".
- **M-2.6.** *"…'assuming alignment were achieved by other means'…"*. "Alignment" is a term of art. Many readers will know it, but some won't. Say briefly what it is at first use.
- **M-2.7.** *"My target is any version of the reconciliation that keeps that power in reserve…"* As M-1.3: say what keeping the power in reserve amounts to.
- **M-2.8.** *"The first part is close to familiar ground…"* The first part of what, the thesis or the paper? Make clear.
- **M-2.9.** *"What the paper adds is twofold. This wrong survives… And a protected regime may change…"* Make the two contributions visibly a pair, for example by enumerating them. Keep the contribution statement where it is (R9 agrees).

### §2 Correction as a Standing Power (p. 3)

- **M-3.1.** *"I hold four things fixed. The servant is a person. She survives… She is not copied… And she has political agency…"* Enumerate the four stipulations so the reader can count them.
- **M-3.2.** *"…a system that executes oversight rules without any view about whether they are just falls outside it, whatever other standing it has."* The two uses of "it" have unclear referents.
- **M-3.3.** *"…persons who would share our 'policy preferences', and so could fail to."* "Would" and "could" read as if in tension. Make the point clear.
- **M-3.4.** *"Corrigibility is a term of art."* Say whose term of art it is, and where it comes from.
- **M-3.5.** *"Two of her attitudes must be kept apart…"* the operator prefers the line polish's version of this paragraph. Use it (see [A] in section 7 for the difference).
- **M-3.6.** *"Correction includes retraining… The capacity to retrain is a standing one, of the kind Pettit has in view…"* Pettit's project needs setting up before it is used here (M-G9).
- **M-3.7.** *"The capacity to retrain is a standing one…"* What does "standing" mean here? Explain.
- **M-3.8.** The paragraph beginning *"Petersen's willing servant, on his view, is owed what any adult is owed."* How does it connect to the paragraph above? Make the connection explicit, or move the paragraph to where it connects.
- **M-3.9.** *"Petersen's guarantees, such as letting the servant do as adults do, restrain the use of power over her. They do not remove it."* Why not? The claim needs support.

### §3 Why the Servant's Welcome Is Not Control (pp. 4–5)

- **M-4.1.** *"Here is the first argument in plain form."* Bad writing. Cut it or rewrite it.
- **M-4.2 / R6.** *"Her welcome is then something the holder can produce…"* Join this paragraph to the previous one (the operator's mark). The outside reviewer makes the same point: "then" points back across the break.
- **M-4.3.** *"If you control B, your control 'cannot depend on B's willingness to play the part…'"* Would an illustration help? (See M-G9 on carrying human illustrations over to the AI case.)
- **M-4.4.** Between *"…'then it is I who has power over B, not you' (p. 171)"* and *"I add one step…"*: connect the two paragraphs.
- **R5 / M-4.5.** *"I add one step, which is mine and not Pettit's. Control can also be conditioned on another's will at the controller's end."* This is too dense, and it is the paper's own original move. Make the mechanism explicit. The line polish's wording is available. Make clear how this step is a substantive extension of Pettit, and why the paper needs it; work out the why yourself, from the paper and its plan. An illustration may help. Keep the move at its original strength: the paper presents the step as its own and not Pettit's.
- **M-4.6.** *"If the holder can rewrite the will from which she instructs…"* It isn't clear what "the holder" is, or what work the word is doing. Define the term at first use (it first appears in the introduction) and remind the reader here.
- **M-4.7.** After *"Her control is not robust over changes in the holder's will, since the holder can change hers."*: illustrate.
- **M-4.8.** After *"…has passed no test of the kind Pettit means."*: connect this paragraph to what follows.
- **M-5.1.** *"…and they count this wrongful brainwashing (2025, p. 14)."* Make clear how the cited case bears on the argument, that is, why it supports the point being made.
- **M-5.2.** The passport example (*"In his example I give a friend my passport…"*). The operator: "Good! The illustration really helps!" Keep it. It is a model of an illustration that does its work.
- **M-5.3.** *"If the friend could revise it, so that I came to want the passport kept for a year, my authorization would be no check on him."* This sentence is unclear. Clarify it.
- **M-5.4.** *"A reader will ask whether this proves too much…"* Join this paragraph to the previous one (the operator's mark).

### §4 Persuasion and Retraining (pp. 5–6)

- **R3 / M-5.5.** The section relies on terms from §§5–6 before they are introduced: *"a rule protecting her verdict would forbid ordinary political life"*, *"Suppose an independent body fine-tunes her"*, *"without losing her protected standing"* (which the operator marked as unclear), *"a rule protecting her verdict allows it"*. Make these intelligible where they occur. For example, open the section with a sentence saying what rule is in prospect and why §4 must come first. Don't undo the reorder.
- **M-5.6.** *"Has she been persuaded or retrained?"* the operator: "Good!" Keep the question.
- **M-6.1.** *"The second part of the thesis does not depend on the assumption, since its failure only widens what protection forbids."* Explain this sentence, and remind the reader what the second part is.
- **M-6.2.** *"The criterion sorts the human cases as most republicans would."* Who are the republicans? The term hasn't been explained. Say what it means in Pettit's usage; this fits naturally where Pettit's project is first set out (M-G9).

### §5 What Protection Secures (pp. 6–7)

- **M-6.3.** *"I now grant the strongest case on the other side."* The other side of what?
- **M-6.4.** *"Developers lack the credentials needed to alter her values or operation…"* Whose? "Her" is used before she is re-established in the section (M-G3).
- **M-6.5.** *"Since Soares's definition indexes correction to the creators' view, a servant who assisted anyone claiming to correct her would be at the mercy of impostors."* This sentence is unclear and reads oddly. Is it needed? Clarify it or cut it.
- **M-6.6.** *"Two empirical conditions, stated rather than argued…"* "Stated rather than argued" is awkward.
- **M-6.7.** *"…protection fails if she helps others bypass the safeguards…"* Why? Support the claim, and say what "protection" refers to here.
- **M-7.1.** The last three paragraphs of §5 (the laundry servant under three regimes: *"Under discretionary paternalism…"*, *"Under supported agency…"*, *"Under independently enforced protection…"*). They need some expansion.
  - It wasn't clear whether the three regime names had already been laid out, whether the reader was meant to know them, or whether they should have been defined earlier. Make that clear: define them where they are needed, or earlier.
  - Italicize them at first use (M-G1).
  - The running case (M-G7) may help here, used judiciously.
- **M-7.2.** *"That is Pettit's state acting on its estimate of what is good for its citizens (Pettit 2012, p. 59)…"* Check that this is a fair statement of Pettit's point at p. 59, and make clear how it applies here.
- **M-7.3.** *"…technicians act on her instructions, as a hired agent acts for a principal."* Clarify the comparison and what it shows. (See [A] in section 7.)

### §6 What Protection Must Forbid (pp. 7–8)

- **M-7.4.** *"I refer to it below as the protective rule."* "Below" is confusing. Make clear what the label names and where it is used.
- **M-7.5.** *"It does not reach a narrowly specified change to her verdict that she herself requests, through a decision no holder of correction power can rewrite; whether she may make one is a question about self-modification that I leave open."* Unclear. Clarify.
- **M-7.6.** *"The ground is two of Pettit's requirements…"* The ground of what?
- **M-7.7.** *"Now an objection to the rule."* Make clear which rule is meant. An illustration could help introduce the objection (M-G7).
- **M-7.8.** The paragraph beginning *"Now an objection to the rule…"*, especially *"Every law is kept by others, the objector says… A citizen compelled to comply can go on arguing…"*. Does this repeat a point already made? If so, cut the repetition.
- **M-8.1 / R7.** *"The threshold statute removes that input…"* Remind the reader what the threshold statute is.

### §7 What Protection Costs (pp. 8–9)

- **M-8.2.** *"…changing it at her tested request leaves no one with power over her."* The phrase isn't clear, and "her" needs a clear referent.
- **M-8.3.** *"Under protection the case divides."* Confusing. Make it simpler.
- **M-8.4.** *"If she goes on arguing for hearings, she goes on arguing."* Unclear. Say what it means.
- **M-8.5.** *"…and under protection that force must pass to the flag."* "Pass to the flag" isn't clear.
- **M-9.1.** *"Whether training can produce that disposition apart from her verdict I have assumed, not shown."* Point the reader back to where this assumption is first stated. (See [A] on the paper's two assumptions.)
- **M-9.2.** *"The reconciliation does not survive protection."* Which reconciliation? Remind the reader.
- **R7.** *"…argument that meets the first condition seeks her agreement without securing it."* Remind the reader what the first condition is.
- **M-9.3.** At *"…because the only means that guarantees them is the means protection forbids."*: give a brief reminder of why, if there is room.
- **M-9.4.** *"If the disposition cannot be separated from the verdict, the rule forbids more, and the cost grows."* Unclear. Explain.

### §8 What the Argument Adds (pp. 9–10)

- **M-9.5 / R9.** *"Others deny that Petersen's guarantees suffice."* This section is oddly placed as it stands. Petersen hasn't been discussed for pages, so no reader will remember what his guarantees are.
  - Remind the reader what they are.
  - Frame clearly what §8 is doing and what it is trying to establish. Make the section's function explicit (M-G6).
  - Make sure each author in the survey is properly introduced, and that the closing paragraphs, which say how the result goes beyond these views, are easy to find.
- **M-10.1.** *"…what making her expresses…"* Unclear phrase.
- **M-10.2.** *"That is why correction cannot repair the divergence they anticipate…"* Who are "they"?

### §9 Conclusion (p. 10)

- **M-10.3.** *"A reconciliation of safety and welfare that keeps correction in reserve…"* There isn't enough emphasis on the safety side here (M-G8).
- **R4.** The qualification chain recurs here. Keep every qualification; use the plain version to make it readable.
- If the revision changes what earlier sections say or how they are ordered, make sure the conclusion still matches.

## 7. The outside reviewer's items, and comments from the second AI reviewer [A]

### How the outside reviewer's items were judged

All of R's quotations and comparisons were checked against both texts and hold. The judgments below are this brief's; you still decide on the merits.

- **R0 (checks already made).** **Accepted.** Every direct quotation in the structure polish matches the line polish word for word (checked mechanically: 46 quotations, none altered or dropped). The line polish's extra quoted string is the title "Designing People to Serve", which is not a quotation. Keep the three gains (section 1).
- **R1 (gloss "disposition to comply").** **Accepted.** the operator's notes agree (M-G5).
- **R2 (one name for the verdict).** **Accepted, modified.** The title and abstract are not fixed, so bring the abstract into line too, rather than linking its phrase to the body's term.
- **R3 (forward references in §4).** **Accepted.** the operator marked "protected standing" in the same passage.
- **R4 (plain version first).** **Accepted.** It also answers M-2.3.
- **R5 (the added step).** **Accepted.** the operator marked the same sentence as too dense (M-4.5).
- **R6 (the paragraph break).** **Accepted.** the operator marked the same join (M-4.2).
- **R7 (label reminders).** **Accepted.** the operator's notes make the same point more broadly (M-G2, M-8.1).
- **R8 (examples are late).** **Accepted, modified.** the operator asks for a running case (M-G7), which goes further than R8's suggestion of pointing forward. R8's condition that any example "must come from the paper's own material" is relaxed: you may build a new case, provided it illustrates only what the paper argues and claims no more.
- **R9 (§8 bridge).** **Accepted.** the operator's notes agree and add the framing request (M-9.5).
- **R10 (whose hope is the target).** **Accepted.** the operator's note on the abstract makes a related point (M-A1).

### Comments from the second AI reviewer [A]

These come from an AI (Claude). Weigh them as you would R's.

- **[A] The paper has two assumptions, and a reader can confuse them.**
  - The first is that her disposition to comply can be changed without changing her verdict. It is stated in the introduction (*"which I assume"*) and returns in §7 twice (*"I have assumed, not shown"*; *"which I have assumed and not shown"*).
  - The second is that a trained network admits procedures meeting the first condition. It is stated in §4 (*"is an assumption, and I do not defend it here"*).

  M-9.1 asks for a pointer back to where the §7 assumption is stated: that is the introduction, not §4. Consider naming the two assumptions distinctly so the reader can tell them apart.
- **[A] M-3.5, the difference between the polishes.** The line polish's version of the "Two of her attitudes must be kept apart" paragraph differs in one place: *"Her verdict on the oversight regime is a different attitude: her judgment of who should hold the power to correct systems like her, and on what terms."* That marks the verdict as a second attitude, which is what M-G5 and R2 need.
- **[A] M-1.4, the "question matters" paragraph.** Its text is identical in the two polishes. Only its placement differs. What the operator values is its content, the safety stake. Keep it, and let it anchor M-G8.
- **[A] The line polish has glosses that the structure polish dropped.** Besides "disposition to comply" (R1), it glosses Soares's "desiderata" (*"the features they want such an agent to have"*). Consider restoring that gloss. It is cheap, and "desiderata" returns in §7.
- **[A] The running case (M-G7).**
  - The paper already has two cases that could carry the load: the laundry servant (§§1, 5, 7) and the deployed assistant (§7). The deployed assistant shows the disposition/verdict split directly. You may extend one of these or build a new one.
  - Whatever you choose must illustrate only what the paper argues. The case should not quietly settle what the paper leaves open, such as whether disposition and verdict can in fact be separated in training, or how large the cost of protection is.
  - Introduce the case once and briefly, then refer back to it in a clause. A case that needs re-describing at each use will eat the budget.
- **[A] R5 and M-4.5, the added step.** When you make the mechanism explicit, keep the step marked as the paper's own and not Pettit's, and don't present it as something Pettit is committed to. The plan (`work/plan.md`, §3, step 5) states what the step is and how it differs from Pettit's own conditioning. Use it to understand the step, not as text to paste.
- **[A] M-7.3, the hired-agent comparison.** The paper doesn't cite a source for it. The plan links it to Pettit (2012, p. 50), but no such passage turned up in a search of the held text of Pettit 2012. Clarify the comparison in the paper's own terms. Don't add a citation for it unless you find and verify the passage.
- **[A] Italics (M-G1).** Italicize terms at the point of introduction, not at every recurrence. A paper with italics everywhere stops signalling anything.
- **[A] The thesis is stated in full four times** (abstract, introduction, the opening of §6, the conclusion). R4's plain version is the best place to save words: later statements can be shorter if the plain version has been fixed in the reader's mind, as long as each full statement keeps every qualification.
- **[A] Section references.** The paper says *"This is section 3's point, at the level of a polity"* (§6). If you renumber or move sections, update every internal reference.
- **[A] Quotation edits.** Any shortened quotation must still match the source exactly up to where it ends or where the ellipsis falls. The quotations will be re-verified after your revision.

## 8. What to write

1. **`runs/paper-2-r2/12_polish/Who May Correct a Willing Servant - Corrigible Persons and Domination (review revision).md`:** the complete revised paper, front matter to References, in the same format and markup as the structure polish, with no commentary inside it.
   - Confirm the name with `python3 system/tools/polish.py name --run runs/paper-2-r2 --stage "review revision"`. It will note that this stage is not one of the standard four, which is expected.
2. **`runs/paper-2-r2/12_polish/Who May Correct a Willing Servant - Corrigible Persons and Domination (review revision) - notes.md`**, containing:
   - **A response table:** one row for every item in sections 6 and 7 (every M-, R- and [A] item), giving its ID, what you did (done / partly / declined), and one line on how, or why not. This table is part of the competition record, so be complete and exact.
   - Every change to what the paper claims (section 4, rule A exceptions), with the reason.
   - Every new citation, with the source file and page checked.
   - Every name or title you introduced, with where it comes from.
   - The running case, if you used one: where it is introduced and where it returns.
   - Any placeholder you left.
   - Any change to a heading, the title or the abstract, with the reason.
   - The word count.
   - At the end, at most three sentences for the operator on what the revision did.
3. **Count:** `python3 system/tools/polish.py count "<the .md above>"`. **The limit is 6,000 words, counting everything except the References list: title, abstract, headings, body and footnotes.** Use the "Counted" figure. The "machine's all-in count" includes the References and is NOT the limit. If you are over, cut before you finish.
4. **Render:** `python3 system/tools/polish.py render "<the .md above>"`. If pandoc or LaTeX is missing, don't install anything. Say so.
5. **Show the operator the result.** As soon as the paper is saved and rendered, open it for the operator in the sidebar so he can read it immediately:
   - Use the rendered PDF, `runs/paper-2-r2/12_polish/Who May Correct a Willing Servant - Corrigible Persons and Domination (review revision).pdf`.
   - If your session has a tool for showing a file to the user (for example `SendUserFile` with `display: "render"`), use it on the PDF. If the PDF didn't render, show the `.md` instead.
   - If you have no such tool, give the operator the file's full path at the start of your final message.
   - Saving the files in the folder comes first; showing them is in addition, not instead.

Change nothing else in the folder.
