---
run: paper-5
call: R-02
role: advisor
mode: respond
recommendation: send
revision_depth: local
decision: send
fixes: 3
from_step: L8
reject_level: 0
improve_level: 8
trend: better
date: 2026-10-23
---

# Diagnosis, round 2

## The review in brief

`send`, depth `local`, moderate confidence. The reviewer accepts the frozen comparison's placement (clearly above *Reference B*, somewhat above *Reference A*, close to the Reference C paper), re-derived the algebra and found it correct, and judges the diagnostic-model paragraph an adequate reply to the strongest objection (additivity goes beyond the asymmetries). It asks for three bounded corrections: P1, bound the intended-benefit paragraph (section 4) and the section 5 inference from "neither did nor allowed" to the lapse of the long-run gain; P2, correct the description of Mogensen 2019; P3, carry the model's idealizations into the assumptions paragraph and abstract. Then: "Correct those locally and stop revising." The architecture report agrees.

## Findings

**1. Intended-benefit premium (section 4): "Such a premium touches only the margin Δ" is asserted, not argued.** Holds, more strongly than the reviewer says; *improve*. If the premium attaches to every benefit the longtermist's life does (she intends a good future) and not to the ordinary agent's unintended future benefits, then V(L) − V(A) = P[(k′−1)B − (k−1)H] + Δ(k′B − kH), positive iff r > r_L, while V(O) − V(A) = b − (k−1)PH is unchanged: the band loses its upper edge, and at k = 2, k′ = 1.01 the escape opens for r above about 100, the paper's estimate for lives like ours. The natural alternative reopens the escape. The result does not need the paragraph, and the model's constant weights already exclude intention-sensitive premiums; the repair is to say so. Entered: work/plan-L4-01.md, step 10: "A premium confined to intended benefits applies at most to the Δ margin, leaving (k − 1)PH whole"; carried into plan.md ("touches only the Δ margin") and draft.md; not tested by work/final-check-2.md.

**2. Agency classification read as exclusion of reasons (section 5).** Holds in part; *improve*. Valid within the model, which weighs outcomes only as done or allowed; but stated categorically, and a deontologist with reasons to promote good not structured by doing and allowing can resist it. The Woollard sentence "Such a condition removes allowing as well as doing, which the escape cannot use" leans on it. Entered: 09_final/round-1/final-L8-01.md, section 5: "If remoteness removed the agent from remote outcomes altogether ... the long-run gain that recommends the longtermist life would lapse with them." work/final-check-2.md I3 restated it ("Woollard's immediacy condition removes doing and allowing together (p. 17)") without testing the step.

**3. Mogensen 2019 misdescribed.** Holds; *improve*. I opened mogensen-2019-staking, pp. 24-27. On the Non-Requiring View an added good life gives a reason with "zero requiring strength" (p. 24). The threat to continuation (pp. 26-27) arises for a McMahan-style view with "no reason to bring into existence lives that are well worth living" and no cancelling weight; on the View+ "we can justify allowing the human race to go on existing" (p. 26). His conclusion offers "reasons to doubt that there is any sound argument from axiological longtermism to deontic longtermism" (p. 27). So "his argument turns on weighting bad lives above good ones, which, he shows, threatens the case for humanity's continuation itself (p. 27)" misstates both his argument and the direction of the p. 27 passage. Entered: the note was accurate (notes/mogensen-2019-staking.md: "On the Non-Requiring View, the goodness of an added life is a purely justifying reason"); the compression began in work/source-check.md, "Bearing": "It shows that weighting future bads asymmetrically against future goods threatens the continuation of the future"; clarity-notes-E-01.md then proposed "his turns on weighting bad lives above good ones"; verification cleared p. 27 on the words, not the use.

**4. Abstract does not flag the model.** Holds; *improve*. "On longtermists' own estimates ... the escape fails unless that extra weight is tiny" reads as following from the premises alone. Entered: work/final-check-2.md, optional fix 1 ("On a simple additive model, the escape therefore needs a further, exact condition"), which was not carried into the delivered abstract.

**5. Two idealizations unstated in the assumptions paragraph.** Holds in part; *improve*. Section 3 lists additivity, constant weights, finite expectations, aggregation and normalisation, but not that the options share the conditional totals B and H (outside the trajectory case) or that an active life changes identities throughout the future. Both are used in the display. Entered: plan.md (model taken as given; round-1 F4); the round-1 repair added the list without these two.

**6. Numerical status in the abstract** ("Using their conservative illustrative figures"). Holds lightly; *improve*; finding 4's repair carries it. **7. Repeated "whole cost, small gain" summaries.** Holds lightly; *improve*; orientation more than padding. **8. "Only the longtermist life is permitted"** means among the three lives; holds lightly; *improve*. None of 6-8 is worth a content pass.

**Not defects.** Section 6 is already conditional. The source items the reviewer could not check are confirmed below.

## Literature claims checked

- Mogensen 2019 `[contradicted]`: confirmed from pp. 24, 26-27 (finding 3).
- Woollard 2015 and the MacAskill appendix `[not accessed]`: held texts opened. Woollard p. 17 "depended on a series of unlikely intervening coincidences", p. 37 "a complete chain of substantial facts", p. 207 "precise delineation of these conditions"; macaskill-2022-wwotf, appendix, "lasts longer than a million years is greater than 10 percent". The paper's uses stand.
- Quinn 1989 page: the held text puts "the building of skyscrapers, highways, and dams" on p. 304; the paper's page and footnote stand.
- Novelty `[unchecked]`: D'Alessandro's coda, the nearest text, was read whole by work/final-check-2.md ("never relates cost to margin, and never treats reach"). Three web searches (the argument by name; identity effects and long-term beneficence; constraints, baseline harms and existential-risk reduction) found only texts already held or cited (the target and GPI summaries, Chappell, D'Alessandro, Mogensen 2019). A bounded check, not clearance.

## Decision

**Send, with three fixes, from L8.**

Will it stand? Yes. The central result (a cost of order (k−1)PH against a gain of order Δ, the exact thresholds, the narrow band, the reach reversal) has survived two outside reviews, a fresh final check and my re-derivation of the band. No finding touches the central inference or its novelty; each can be repaired by narrowing or deleting text, with no new inference or source. Its chance: the frozen comparison puts it above two competitors and close to the strongest, so it is a credible competition entry and a credible general-journal submission. Its main exposure, that additivity does more than the asymmetries, is met by the diagnostic-model paragraph. A rewrite costs an author pass, a final check, clarity and verification, and in round 1 a rewrite introduced the necessity claim that became the reject-level finding; nothing here needs that risk. Seven days remain; fixes and verification take a day.

Where I differ from the reviewer. (i) Its conditional rewording of the intended-benefit paragraph would invite the other case, which reopens the escape; I place the view outside the model instead. (ii) Section 5's inference is valid within the model, so the repair is wording. (iii) I do not shorten the summaries to fund the scope clause; the fixes are nearly word-neutral.

Length. The verifier's corrected count (09_final/verification-note.md) is about 5,471 all-in against the 5,500 ceiling. The fixes below are designed to be roughly word-neutral (about −57, +4, +15, +40, +2). If the corrected count after the fixes exceeds 5,500, replace Fix 1(a)'s sentence by deleting the paragraph entirely; cut nothing else.

## Fixes

Make exactly these changes and nothing else. Old text is quoted exactly from 09_final/final.md.

**Fix 1 (P1, two places): bound the ancillary claims.**

(a) Section 4, replace the whole paragraph beginning "A different premium might be proposed." (through "in their Medicine case (p. 5).") with:

> A premium confined to intended benefits would lie outside the model, whose weights do not vary with the agent's aims, and I leave it aside.

(b) Section 5, replace

> The limit must take a particular form. If remoteness removed the agent from remote outcomes altogether, so that she neither did nor allowed them, it would remove her from remote benefits too, and the long-run gain that recommends the longtermist life would lapse with them. The view the escape can use is that remote harms are counted, but at the weight of harms allowed.

with

> The limit the escape uses takes a particular form: remote harms are counted, but at the weight of harms allowed, while remote benefits keep the weight that recommends the longtermist life. A view on which remoteness removed remote outcomes, benefits as well as harms, from the agent's practical assessment would not supply this escape.

and, in the Woollard paragraph, replace "Such a condition removes allowing as well as doing, which the escape cannot use." with

> Such a condition decides whether there is doing or allowing at all, not how much a harm done weighs, so it does not by itself supply the escape's limit.

**Fix 2 (P2): describe Mogensen 2019 accurately.** Section 3, replace

> Mogensen (2019) is the other antecedent; his argument turns on weighting bad lives above good ones, which, he shows, threatens the case for humanity's continuation itself (p. 27).

with

> Mogensen (2019) is the other antecedent. He doubts that the value of the future makes improving it obligatory when the improvements change who will exist, and he explores a view on which the goodness of an added life gives a purely justifying reason, with no requiring strength (pp. 24, 27).

The verifier checks against mogensen-2019-staking pp. 24 ("zero requiring strength") and 27 ("reasons to doubt that there is any sound argument from axiological longtermism to deontic longtermism").

**Fix 3 (P3, two places): carry the model's scope.**

(a) Abstract (must stay at most 150 words; it is 148 now and 150 after these three replacements). Replace "a long-term focus alone does not secure it." with "long-term focus alone does not secure it." Replace "so it does harms that inaction would merely allow." with "so it does harms that inaction merely allows." Replace "On longtermists' own estimates for an individual, in a future like ours, the escape fails unless that extra weight is tiny." with

> In an additive model using longtermists' own estimates for an individual in a future like ours, the escape fails unless that extra weight is tiny.

(b) Section 3, the model paragraph: after "and a common weight of 1 for allowing harms and allowing benefits." insert

> Except in the trajectory case below, it also assumes that acting changes only the probability of a long future, not its expected benefit $B$ and harm $H$, and that an active life changes who exists throughout that future.

## Brief for the next pass

The next call makes the three fixes above and nothing else; the verifier checks them against this file and the counts. Keep everything else: the title, the order of sections, the derivations, the floor-and-illustration qualifications, the diagnostic-model paragraph, the D'Alessandro contrast and the conditional section 6. Do not add a theory of remoteness, a representation theorem or another model, and do not reopen thesis selection.

Pressure to keep in mind if the operator later edits or a referee writes. (1) The strongest objection is the additive representation; the answer is the diagnostic-model paragraph, now with its two idealizations stated. (2) An intention-sensitive benefit premium that covers all the benefits the longtermist intends would reopen the escape above r_L (finding 1); the paper's answer is scope, and no later pass should reinstate a categorical dismissal. (3) "Only the longtermist life is permitted" means among the three lives compared. (4) Section 5's claim is about what the escape uses, not about what every agency-based view must lack. (5) The polish, if the operator asks for one, must not run on the current word counter (Machine notes, 1).

## Effect of the last machine change

v14.8 (2026-10-22) made the polish budget the 6,000-word limit with title and abstract counted, predicting "more room for the polisher on every paper", with the risk of a longer paper, and relying on the counter's "higher of two counts" as the only margin. No polish has run on paper-5, so the prediction cannot yet be compared. But this round shows the margin fails on a mathematical paper: `polish.py count` on 09_final/final.md reports "Counted ... 3380" and "Polish budget: 6000 (room for 2620 words)", while the verifier's corrected all-in count is about 5,471. Both of the counter's counts lose the text between a bare `<` and the next `>`. A polish run on this paper under v14.8 would be told it has about 2,600 words of room it does not have, and `check`, using the same counter, would pass a text over the limit.

## Machine notes

1. **Repair the counter before any polish of paper-5** (R4): the `polish.py count` output above; work/rewrite-note.md, work/clarity-response-E-04.md and 09_final/verification-note.md each worked around it. Cost: a tool fix and regression cases; no calls.
2. **Make the round-1 R1 adoption.** lean/roles/advisor.md still reads "Name the inferences its abstract relies on (at most three)"; work/final-check-2.md cleared findings 1 and 2. Cost: about 60 words; no call.
3. A final check's optional scope fix should be made or declined on the record (finding 4). Once; covered by 2 if R1 tests the abstract as delivered.

Architecture report: R1, R4 adopt; R2, R3, R5, R7 test; R6 reject; Proposal A through R1 and R4 only; Proposal B reject for production.

## Weighing machine changes

- **R1 (literal claim test in final check).** (a) work/final-check-2.md I3 restated the section 5 step untested; work/final-check.md (round 1) cleared necessity. (b) Recurring: paper-5 rounds 1-2, paper-4 round 1 (EVOLUTION v14.7). (c) About 60 words, no call; it changes the step that keeps failing. **Adopt** (adopted in round 1, not yet made).
- **R2 (separate the supported payoff from its extension).** (a) work/choice-2.md: "The bare inequality alone would be a note." (b) One run; this round's findings do not trace to it. (c) Changes selection; large confound. **Test**, as in round 1.
- **R3 (contextual check of decisive paraphrases).** (a) work/source-check.md "Bearing"; verification cleared p. 27 on the words. (b) Once (none in EVOLUTION); plan-check already asks "Is any author misdescribed?". (c) A few reads per run. **Test**: adopt on a second misdescription reaching review.
- **R4 (counter and clarity-checker repair).** (a) verification-note.md and the polish.py output above; E-05's no-change call. (b) Recurring in this run (rewrite, clarity, verification, packet), and live for the next polish. (c) Tool maintenance only; no confound. **Adopt.**
- **R5 (staged acquisition, neighbour search).** (a) Unruh 2025 missing until intake (round 1). (b) Once. (c) Changes the largest cost block. **Test**, outside production.
- **R6 (conditional clarity).** (a) No quality failure; a cost argument. (b) n/a. (c) Resets clarity measurement. **Reject** this round.
- **R7 (stale pointers, usage rows).** (a) architecture-review §2: the stale pointer, met in both audits; the v12.4 addendum fixed the map once before. (b) Recurring. (c) Tiny. **Test** only because of the two-adopt limit; the operator may treat it as maintenance.
