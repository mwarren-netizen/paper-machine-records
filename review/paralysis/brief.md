# Revision brief: paper-5, review revision

**Paper:** "Can a Deontologist Escape Paralysis by Living for the Long Term?"
**Run:** `runs/paper-5`
**Text to revise:** `runs/paper-5/12_polish/Can a Deontologist Escape Paralysis by Living for the Long Term (line polish).md` (5,548 words by `wc`; use the count command below for the official figure)
**Output stage name:** `review revision`
**Prepared:** 2026-10-24

---

## 1. What this task is

The line polish of this paper has been read on paper by the human who runs the machine (the operator) and by two AI reviewers. This brief collects all of their feedback. Your job is to write one revised version of the paper that answers it. The revision combines line-level and structural work: it may reorder material, add explanations and examples, and move or condense passages, as set out below.

There is a lot of feedback here, and all of it is meant to be acted on. Work through every item. You may decline an item, but only for a reason, and you must record what you did with each one (section 8).

## 2. The rule you are working under

The paper is an entry in a competition that requires the essay's substantive philosophical content to come from AI. A human may point out that something is unclear, underdeveloped or out of order, ask for an example or a rewrite, set length and format constraints, and ask for material to be cut. A human may not supply arguments, premises, distinctions, objections, examples or wording.

So:

- **The human's notes are generic on purpose.** They say where a careful reader got lost and what kind of fix is wanted. They never tell you what the fix is. Work the solution out yourself, from the paper, its sources (`runs/paper-5/02_corpus/`) and its plan (`runs/paper-5/work/`).
- **If you notice that a human note seems to point toward a particular philosophical claim, don't add the claim on the note's authority.** Decide on the merits, as you would for any change.
- **The AI reviewers' suggestions are AI-originated.** You may use them, but they are suggestions, not instructions: accept, modify or reject each one on its merits, and say which.
- **Don't look for other human input on this paper.** The record of the review is `runs/paper-5/methodology/human-review-log.md`. It is redacted and adds nothing to this brief. You don't need to read it.

## 3. Sources of feedback

- **[H] Human reader (the operator):** margin notes on a printout of the line polish, plus a spoken pass. They are given here in generic form, with IDs matching the review log (H-1.1, H-2.1, …). Page numbers refer to the rendered line polish PDF (`PAPERS/… (line polish).pdf`). Every note also quotes the passage it concerns.
- **[R] Outside AI reviewer:** `runs/paper-5/methodology/outside-reviewer-suggestions-2026-10-24.txt`. **Read it in full.** It is cited here by item (R2(c), R7, …).
- **[A] Second AI reviewer:** comments from the Claude session that prepared this brief. They are marked [A] and collected in section 7.

## 4. Which rules from `POLISH-LINE.md` still apply

Read `POLISH-LINE.md`. Its guiding principle, **cognitive empathy with the reader**, applies in full: it is the point of this revision. Its hard constraints apply as follows.

**Still in force:**

- **A (change nothing the paper claims).** Two exceptions: (i) where you accept an AI reviewer's correction (e.g. R2(c)); (ii) where a requested explanation needs you to state a step the paper leaves implicit. List every such change in your notes.
- **C (names and titles only from the References list or `02_corpus/bibliography.md`).**
- **D, quotations and citations:**
  - Every direct quotation stays word for word, with its citation attached.
  - You may shorten a quotation only by ending it earlier, or by marking an omission with an ellipsis. Never alter its words.
  - Don't add italics inside a quotation unless you mark "emphasis added".
  - Page references stay attached to the same claims.
  - Markdown conventions stay as they are.
- **Anonymity.** Add nothing that identifies the author.
- **F (6,000 words, hard).** The limit counts everything except References: title, abstract, headings, body and **footnotes**. Moving text to a footnote saves no words.

**Relaxed for this revision:**

- **B (add no new content).** You may add:
  - plain-language glosses of the math
  - examples
  - a summary paragraph
  - a preview of the paper's results in the introduction
  - signposts
  - footnotes

  where the feedback asks for them. You may also add a sentence an AI reviewer suggests, if you accept it.
- **New citations.** Only for a work that is already in `02_corpus/bibliography.md` and whose text is held in `02_corpus/sources/`. Check every quotation and page reference against the source. If you can't check it, leave it out.
- **D, structure.** You may move material between sections (the introduction needs reordering; one passage moves to a footnote). Keep the section headings and their order unless a move makes a heading inaccurate. If you change one, say so in your notes.
- **D, title and abstract.** Leave both unchanged unless your revision makes the abstract inaccurate. If you change it, say why in your notes. Note that the abstract counts toward the limit.
- **E (no roadmaps).** Signposting that the feedback asks for is allowed: the intro preview, the state-of-play paragraph, and the roadmap within §3. Everything else in E still applies: no throat-clearing, no filler, no closing sentences that restate the paragraph.

## 5. Priorities and word budget

The line polish is close to the limit (`polish.py count` gives the official figure), and the feedback adds a lot. Spend words in this order:

1. **Plain-language translations of the math. This is the top priority, and most of the spare words should go here.** The human reader says the math is good but too often left untranslated. The model is a sentence the paper already contains in §5: *"Roughly, this is the condition that the longtermist life does more expected good than the ordinary life once the asymmetry is set aside."* Wherever a formula, condition or threshold matters to the argument, give a rough statement of what it means in that spirit. If a formula has no honest plain version, say what it does rather than force one.
2. **The introduction's framing and order** (H-1.1 to H-3.1 below).
3. **Explanations of steps a reader couldn't follow** (H-2.2, H-2.5, H-3.6, H-8.1 and others).
4. **Examples where requested** (H-3.4, H-6.1, H-8.4).

**Make room by:**

- trimming §5 substantially (H-8.2)
- shortening the Woollard paragraph (H-9.1)
- condensing the "Other replies" paragraph (R8)
- condensing the comparison with D'Alessandro at the end of §3 (H-6.2)
- cutting anything else that isn't pulling its weight

## 6. The feedback, section by section

### Conventions for the whole paper

- **H-G1, italics for terms of art.** Italicize a specialized term at the point where it is introduced or defined (e.g. *proportional margin*, *stakes-sensitivity argument*), so the reader knows to attend to it.
- **H-G2, italics for "does" and "allows".** Where "does" or "allows" is used in its technical sense and the ordinary reading would mislead (e.g. "ordinary life *does* them"), italicize it. "Doing harm" sounds odd in ordinary English, and the italics tell the reader it is a special use. Apply the rule consistently rather than at random. No added italics inside quotations unless marked "emphasis added".
- **H-G3, reminders.** Where the argument turns on a symbol introduced pages earlier, remind the reader what it stands for. The notes below flag several places, but apply this wherever it's needed.

### Introduction (pp. 1–2)

- **H-1.1 / H-1.2.** *"Suppose you hold the ordinary deontological view…"* and *"They treat the argument as a reductio of these asymmetries."* The introduction doesn't make clear why paralysis is a problem for the deontologist in particular. Make that clear, and introduce the two asymmetries by name, so that "these asymmetries" has something to refer to. (Related: R3, R7.)
- **H-1.3.** *"…then the reasoning behind paralysis seems not to forbid it."* This says the reasoning behind paralysis seems not to forbid long-term beneficence, but doesn't say why. The paper's explanation comes only in §2. Readers need it here, or need to have been given it before this point.
- **H-3.1 (structural, high priority).** The explanation of why the long-term escape seems to work comes in §2 (*"An act whose point lies in the long run is not weighed that way"* and the paragraph beginning *"This is offered as a possible escape, not a demonstrated one"*). By then, the introduction has already stated results that depend on it. Readers need the Paralysis Argument and the escape explained before the results. Reorder accordingly.
- **H-2.1.** The opening of p. 2 (*"promising response involves accepting…"* through *"Can a deontologist who accepts its premises avoid paralysis by living for the long term?"*) is hard to follow. It isn't clear who is advising whom, or why both the Paralysis Argument and the longtermist claim matter to the question. Step back and frame the question before giving results.
- **H-2.2.** *"…accepting what in practice amounts to a highly demanding morality of beneficence with a long-term focus."* Unclear: what is this, and how is it supposed to avoid paralysis? (Related: R6.)
- **H-2.3.** At *"The price is demandingness"*: if demandingness is taken up later in the paper, signpost that here.
- **H-2.6a.** Several terms on p. 2 come without enough context for a newcomer, including *"living for the far future"* and *"side-constraints"*. Explain each at first use.
- **H-2.5.** The paragraph quoting Greaves and MacAskill (*"these are not circumstances where one is required to violate side-constraints…"*). It isn't clear how this longtermist claim bears on the paralysis problem. Explain the connection.
- **H-2.6.** *"Living for the long term is itself identity-affecting: it too changes who will exist."* "It too" is unclear: too as what? Make the comparison explicit.
- **H-2.7.** *"That cost scales with the probability that there is a long future at all. Its gain scales with how much one agent raises that probability…"* These claims are stated without explanation in the introduction. Explain them, or hold them until they can be explained.
- **H-2.9.** The paragraph beginning *"Suppose instead that the extra weight of doing harm does not reach the whole future…"*. **Keep it in the main text.** It doesn't say why it matters, so readers can't see what §5 is for. Make its role clear. (Related: R5; see [A] in section 7.)
- **H-2.10.** *"William D'Alessandro (2022) has already argued that, on their premises, the escape fails…"*. At D'Alessandro's first mention, the contrast between his argument and this paper's is unclear. The paper states it more sharply at the end of §3. Make the contrast clear where he is first introduced. Consider whether this sentence belongs in a footnote.
- **R5.** Consider previewing the paper's three cases in the introduction, so readers can see its structure.

### §2. The Paralysis Argument and the longtermist escape

- **H-3.4a.** "Identity effects" is used before it is explained. Define it at or before first use.
- **H-3.3.** *"Mogensen and MacAskill reject the reply that intervening agency breaks the chain (pp. 8–9)."* Consider whether this sentence belongs in a footnote.
- **H-3.4.** *"An ordinary act does the harms that inaction would allow, and the extra weight on doing harm swamps any foreseeable benefit."* Would an example make this clearer?
- **H-3.5.** In the quotation ending *"…We are no longer weighing the short term against the long term" (p. 14)*: consider cutting the last sentence of the quotation. If you cut it, end the quotation earlier or mark the omission with an ellipsis.
- **H-3.6.** *"…the price is that 'your every motion must be at the service of posterity' (pp. 14–15)."* Why does this price follow? The paper reports it without explaining it. This was the main thing a careful reader could not work out in the opening pages, and he marked it three times. Make the answer clear. (Related: R6.)
- **R3.** Name the two asymmetries explicitly, tie each to its parameter, and say why paralysis needs both. (See also H-1.1.)
- **R6.** Make explicit where the escape's demandingness comes from.

### §3. What the longtermist life costs

- **H-4.1.** Translate the notation into plain words. A careful reader lost track of what k and k′ stand for.
- **H-4.2.** *"To make the comparison exact, assign weights to doing and allowing. Doing harm has weight k > 1 and allowing harm has weight 1…"* This reads like a result rather than an assumption of the model. Present it clearly as an assumption, since it orients the reader for everything that follows.
- **H-5.1.** *r > k + (k − 1)/ε.* Say in words what this condition means.
- **H-5.2.** *"What it offers in return is Δ(B − kH), a gain proportional to the margin."* Remind the reader what ε is where it's used here.
- **H-5.4.** The paragraph beginning *"That estimates r for a world like ours."* Consider whether it belongs in a footnote. (Weigh this against R2(f), which wants this paragraph's last point made more explicit.)
- **H-5.5.** *"With k = 1.000001 and ε = 10⁻⁷…"* Remind the reader what k is here.
- **H-5.6.** The paragraphs on a tiny premium and the Rescue case. Signpost where this part of the section is going.
- **H-5.7.** *"…ordinary life stays forbidden if b is below 10⁻⁶PH"* and *"…the size of the future multiplies B and H alike…"*. Remind the reader what b, B and H are where the argument turns on them. (See [A] on b and B.)
- **H-6.1.** *"The inequality says exactly how much better an unusual career would have to do."* This could become an example that gives the reader a sharp contrast to consider. Would one help?
- **H-6.2.** The paragraph closing §3 (D'Alessandro, and Mogensen 2019):
  - **Condense** the comparison with D'Alessandro, keeping it in the main text.
  - **Move** the discussion of Mogensen (2019) (*Staking Our Future*) to a footnote.
  - The paper's statement of its own contribution (*"What is new here is therefore not the verdict that the escape fails, but the location of its cost…"*) currently sits in this paragraph. **Keep it in the main text and make it clearer and more visible.**
- **H-6.3.** Before §4, add a short paragraph summarizing where the argument stands.

### §4. When doing a benefit carries a premium

- **H-6.4.** The formula for r_L. Give a plain-language version of this threshold if one is possible. If it can't honestly be put plainly, say what it does. (Related: R2(a), (b).)
- **H-7.0.** The first full paragraph of p. 7 (*"If r < r_L, only stillness is permitted… The asymmetries forbid nothing in this region."*) carries a lot of the argument. Go through it slowly, with the newcomer in mind.
- **H-7.1.** The three regions (r < r_L; r_L < r < r_O; r > r_O) are hard to follow. Say in words what each threshold is and what each region means. (Related: R2(a), (e).)
- **H-8.1.** *"Demandingness alone does not secure them."* (the last sentence of §4). A careful reader was "totally flummoxed": it wasn't clear what this means or how it follows. Explain.
- **R2(a)–(f).** All of R2 is relevant here. Note R2(c) especially: it identifies a sentence (*"The longtermist life now has a second source of value: the extra weight on the benefit it does"*) that invites misreading.

### §5. Limiting the reach of the premium on doing harm

- **H-8.2.** The purpose of §5 isn't clear when the reader reaches it. Make its role clear, and preview it in the introduction (H-2.9). **Cut §5 down substantially to make room elsewhere, while keeping what the section is for.** (Related: R8, which explains what the section does for the paper.)
- **H-8.3.** §5 doesn't say why anyone would consider limiting the premium's reach. Motivate it, or say why it is worth considering. (This adds words while H-8.2 removes them. Balance the two.)
- **H-8.4.** The passage around the condition H_T/H < ε(r − 1)/[(1 + ε)(k − 1)] is heavy on algebra without a gloss. Give an example.
- **H-9.1.** The Woollard paragraph (*"Woollard's (2015) account in Doing and Allowing Harm gives no more help."*). Is it needed at this length? Shorten it, or cut it if it can go. (See [A] in section 7.)
- **R8.** Condense the "Other replies" paragraph.

### §6. What deontic longtermism must assume

- **H-10.1.** *"Greaves and MacAskill's case for strong longtermism includes the stakes-sensitivity argument."* This appears to be the argument's first appearance. Introduce it properly as an argument (whose it is and what it is) before discussing its premises. Check whether "the" or "a" is right, against Greaves and MacAskill's own usage. Italicize it at first use (H-G1).
- **H-10.3.** The paragraph beginning *"One might reply that the constraint engaged by the unforeseeable deaths of future people is not serious."* This is very hard to follow. Explain it as plainly as possible.

### Conclusion

No notes. If the revision changes what earlier sections say or how they are ordered, make sure the conclusion still matches.

## 7. Comments from the second AI reviewer [A]

These come from an AI (Claude). Weigh them as you would R's.

- **[A] The horizon result.** It is the third of the paper's findings: the last sentence of the abstract, and a third of the conclusion. That is why H-2.9 keeps its setup in the introduction and H-8.2 trims §5 rather than cutting it.
- **[A] The contribution statement.** "What is new here…" is the paper's only explicit statement of its contribution. Wherever the condensed D'Alessandro comparison ends up, this statement should be easy to find, and probably foreshadowed in the introduction.
- **[A] R2(c) is a real error, not a matter of style.** Ordinary life also gets the extra weight on the benefits it does, so the sentence points at the wrong difference between the two lives.
- **[A] R2(b).** The weighted-average (mediant) formula adds algebra to the section that already has the most. Prefer the verbal explanation. Put the formula in a footnote or leave it out.
- **[A] R4's analogy ("signing your name to the whole future").** Use the idea if it helps, but don't paste it in.
  - "So the escape works only by coincidence" claims more than the paper does. The paper hedges ("for the illustrative weights and small individual margins considered here").
  - "For a future like ours, the scale tips slightly against signing" depends on the weights. With the paper's own illustrative §4 weights (k = 2, k′ = 1.01, so r_O = 100) and its estimate of r for lives like ours ("a few hundred"), ordinary life may already be permitted.
  - Build any example or picture yourself, and check it against the paper's numbers.
- **[A] R7.** The k = k′ = 1 point needs no new citation. Of the cluelessness references, Greaves (2016) is in the bibliography, but it is held only as an author's draft with no published page numbers, so quote it only if a page reference isn't needed. Lenman is not in the bibliography, so don't cite him.
- **[A] b and B.** A careful reader read the "b" in *"ordinary life stays forbidden if b is below 10⁻⁶PH"* as capital B. The paper uses lower-case b (an ordinary life's foreseeable benefit) and capital B (the long future's expected total benefit) a few lines apart. Reminders, or clearer handling of the two, are especially needed here.
- **[A] Woollard.** If you cut the Woollard paragraph entirely, the introduction's claim that neither Quinn nor Woollard supplies the needed limit loses its support. Shortening is safer, and if you cut it, change the introduction's claim to match.
- **[A] Quotation edits.** Any shortened quotation must still match the source exactly up to where it ends or where the ellipsis falls (see H-3.5). The quotations will be re-verified after your revision.

## 8. What to write

1. **`runs/paper-5/12_polish/Can a Deontologist Escape Paralysis by Living for the Long Term (review revision).md`:** the complete revised paper, front matter to References, in the same format and markup as the line polish, with no commentary inside it.
   - Confirm the name with `python3 system/tools/polish.py name --run runs/paper-5 --stage "review revision"`. It will note that this stage is not one of the standard four, which is expected.
2. **`runs/paper-5/12_polish/Can a Deontologist Escape Paralysis by Living for the Long Term (review revision) - notes.md`**, containing:
   - **A response table:** one row for every item in section 6 (every H-, R- and [A] item), giving its ID, what you did (done / partly / declined), and one line on how, or why not. This table is part of the competition record, so be complete and exact.
   - Every change to what the paper claims (section 4, rule A exceptions), with the reason.
   - Every new citation, with the source file and page checked.
   - Every name or title you introduced, with where it comes from.
   - Any placeholder you left.
   - Any change to a heading, the title or the abstract, with the reason.
   - The word count.
   - At the end, at most three sentences for the operator on what the revision did.
3. **Count:** `python3 system/tools/polish.py count "<the .md above>"`. It must be at most 6,000.
4. **Render:** `python3 system/tools/polish.py render "<the .md above>"`. If pandoc or LaTeX is missing, don't install anything. Say so.

Change nothing else in the folder.
