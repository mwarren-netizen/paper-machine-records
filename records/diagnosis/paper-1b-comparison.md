# paper-1b against paper-1: comparison and what the run taught

Date: 2026-10-11. paper-1b re-ran V12 to V20 on paper-1's V00 to V11 material, under the v3-candidate machine (`system/CHANGES-v3.md`). Both finals are complete:
- `runs/paper-1/09_final/paper.pdf`: 5,361 words.
- `runs/paper-1b/09_final/paper.pdf`: 5,328 words.

## Bottom line

paper-1b is the stronger paper.
- Two blind judges both preferred it clearly. Each read the two finals under neutral labels, in opposite orders.
- A first reader stalls on it less often.
- Most of the stalls that do remain are of kinds a paper of this density will always have, not the referent failures that sank paper-1's opening.

It is not a finished success. The introduction still carries too many definitions, and length pressure still cost some examples.

## 1. Blind paired judgement (Opus, editor of a general journal)

| Judge | Order shown | Preferred | Strength | paper-1 scores (readability / argument / publishability) | paper-1b scores |
|---|---|---|---|---|---|
| 1 | paper-1 first (A/B) | paper-1b | clear | 5 / 7 / 6 | 8 / 8 / 7 |
| 2 | paper-1b first (P/Q) | paper-1b | clear, not by a wide margin | 6.5 / 6.5 / 6 | 7 / 7.5 / 7 |

Why the judges preferred paper-1b:
- Its worked numbers make the problem concrete.
- Its anchor dilemma claims to cover every case.
- It meets the stakes objection directly.
- Its positive account covers a firm view with nothing opposed to it.

What they would take back from paper-1:
- the three-claim framing;
- the second-person opening;
- the contrast between contingent and constitutive dependence;
- the definitions of "outlasts" and "erases".

Both judges also flagged production residue in paper-1b's footnotes: "PDF 11", "draft pages" and "offprint pages". Reports: `diagnosis/compare/judge-AB.md` and `judge-PQ.md`. The key to the labels is in `key.txt`.

## 2. First-reader stall counts (same protocol, Sonnet)

| Text | Words | Stalls | Per 1,000 | R | T | S | Q | D |
|---|---|---|---|---|---|---|---|---|
| paper-1 final body (read 10 Oct) | 5,058 | 63 | 12.5 | 18 | 11 | 15 | 4 | 15 |
| **paper-1b final body** | 5,013 | 52 | 10.4 | 9 | 10 | 13 | 4 | 16 |
| paper-1 introduction (re-read today) | 845 | 25 | 30 | 10 | 6 | 2 | 3 | 4 |
| **paper-1b introduction** | 878 | 24 | 27 | 3 | 7 | 8 | 1 | 5 |
| Control: Sepielli 2012, introduction | 1,159 | 24 | 21 | 3 | 8 | 5 | 1 | 7 |

Referent stalls are halved in the body (18 to 9) and fall from 10 to 3 in the introduction, which is the control's level. That was the defect behind the opening sentence of paper-1. The introduction's total barely moves, because its stalls have changed kind:
- Steps asserted without argument rose from 2 to 8. The introduction states the anchor dilemma's verdict and that "betting cannot measure" before the body argues them.
- Term stalls held steady (6 against 7): the introduction now glosses eight terms, and a reader still meets them all on page one.

The desk-reject reader at V18 said the same: "many definitions … and a footnote on nearly every sentence."

## 3. What changed in the machine's behaviour

- **Selection.** In paper-1, 23 of 39 selections went to pass a. In paper-1b the winning passes were a 11, b 8 and c 11 of 30, so the position bias is gone. In all 30 units the selector chose the draft the blind ranking put first.
- **Proportions.** The outline followed the V11 judge's advice. The central argument (S2) grew from 1,149 to about 1,970 words, and the secondary account (S3) shrank from 963 to about 665.
- **The opening.** paper-1b opens with Ramsey's rain bet and the editor's question. A referent always comes before its question.
- **Cuts.** The V17 cut, about 290 words, took only citations and reference apparatus and left the body untouched. paper-1's cut took 170 words of body.
- **Reader checks.**
  - The first reader logged 19, 22, 20, 21 and 8 stalls before the five section closes, and 44 on the whole body at V17.
  - The closes answered every stall.
  - At V17 the author fixed 40 of the 44 and rejected 4 with reasons. The V17 editor checked those rejections.
- **Referees.** The unsympathetic referee claimed a fatal flaw: that settlement, not concern, drives the anchor dilemma. The judge dismissed it and the author repaired the wording in S2. paper-1 drew no such claim. One reading is that S2 is now explicit enough to attack.

## 4. Problems the run exposed (for v3)

1. **Writers fill the band.**
   - Every pass aimed at the +25% ceiling, so every section reached its close about 25% over budget.
   - The install had removed v2's 10% section slack; I restored it mid-run (logged as a deviation).
   - The closes then still had to cut about 12%. The S2 close cut two examples (the skier and the packed glass) and rejected a worked calculation a reader had asked for.
   - The binding constraint is the conservative word budget: target 5,000, with about 900 for notes and references.
   - Options for the operator: tell writers to aim at the budget and keep the band for the selector; or raise the target toward the ceiling. Most papers have room below 5,500.
2. **The citation roster competes with intelligibility.** The early footnote naming every party and the gloss-every-term norm together pack page one. The operator could relax one of the two for the introduction only.
3. **The brief needed the draft.** As installed, the writer's brief could not see what the reader already had. The card was fixed at S2, and the S2 brief was rerun.
4. **`blind/spec.md` sits beside the blind drafts.** The ranker noticed it was there, though it did not read it. Move it out of `blind/`.
5. **Production labels survive into the PDF footnotes.** Examples: "(offprint pages)", "PDF 11". The verifier's mechanical labelling should go into the verification note, not the text.
6. **Scratch files.** Subagents left about 20 empty `.tmp` files and one splice script in `runs/paper-1b/07_prose/`. Deletion is off in this folder.
7. **Cost.** 205 calls for V12 to V20, against 199 in paper-1. Each unit cost five calls instead of four, but paper-1b had 30 units against 39. (An earlier draft of this file said 271; that figure wrongly counted the 65 V00 to V11 calls copied into paper-1b's log.)

## 5. Caveats

- The three V18 referees in paper-1b ran on Opus by my error; the spec names Sonnet, and paper-1's referees were Sonnet. paper-1b's revision therefore answered stronger reports. This was logged as a deviation on 2026-10-12. It is a confound. Before review the two drafts are hard to compare on stalls: paper-1b's body at V17 had 10.2 per 1,000 words, and paper-1's first full draft 9.5, but paper-1's draft was 1,800 words longer and longer texts stall less per word.
- There is one paper and one run per condition, and the judges and readers are models.
- paper-1b also had sources paper-1 lacked: Schervish, Seidenfeld and Kadane, Karni and Schmeidler, and Baccelli. Its worked numbers owe something to them. That is the C3 norm working as designed (show a borrowed result once), but it is not purely a change in exposition.
- Whether the corrections cause new problems in a different paper is still untested. A second paper is the real test of the machine.
