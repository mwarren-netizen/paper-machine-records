# V21 architectural audit — paper-5, review round 2

## 1. Executive diagnosis

**Keep the current harness for this submission. Repair several specific mechanisms; test simplification on research notes before replacing the pipeline.** Stage 1 recommends sending the paper after bounded local corrections. Inspection of the production history does not change that judgment, and the saved philosophical review remains frozen.

The harness generated a worthwhile argument, rejected inadequate alternatives, acquired consequential sources, and corrected its principal overclaim after outside review. It is not merely polishing an insignificant thesis. Its main weakness is the movement from a supported conditional result to stronger claims about what follows necessarily, what a source establishes, or what every alternative must assume.

Three mechanisms deserve the most immediate attention:

1. Change the existing argument check so that it tests the literal strength of the advertised conclusion, rather than validating several premises while leaving their conjunction's supposed upshot untested.
2. Check the context and inferential use of a few decisive paraphrases, not only the accuracy of quotations and page locators.
3. Repair deterministic checks that misread mathematical text or formatting changes, and stop spending strong-model calls on their false alarms.

The evidence for those failures is high-confidence. The claim that a substantially shorter pipeline would produce equally good research is a hypothesis requiring an experiment. No additional standing reviewer is justified by this run.

## 2. Identification, boundary, and evidence

Stage 1 was saved before I opened V21-HARNESS-MAP.md, STATE.md, or any production artifact. Its SHA256 is:

`b23deb62061b4f338e57fcd2fa9ef7ed45d2262917beeda52364be6d0cd01c35`

The frozen comparison checksum was verified before Stage 1 and was not changed.

The relevant run is **runs/paper-5**, machine **v14.8**, awaiting its second publication review. REVIEW/paper.md is byte-identical to runs/paper-5/09_final/final.md. STATE.md's canonical fields establish the current run; the static audit map's account of “round 3” and paper-1-r5 is historical and materially stale for this packet. I initially inventoried that older path, then resolved the discrepancy before reading its production records or attributing costs. The first audit independently encountered the same stale pointer. This is now a repeated navigation problem, not evidence about the older paper's quality. [Evidence: STATE.md; V21-HARNESS-MAP.md, final section; runs/paper-5/10_review/round-1/architecture-review.md, §2.]

All subsequent run-relative paths below refer to **runs/paper-5/** unless explicitly prefixed with lean/, system/, or another root file. I inspected role instructions, the selected and rejected proposals, plans and checks, drafting and rewrite records, clarity records, source notes and relevant source passages, the first review's response, and the call/deviation/event logs. I did not operate the harness, edit its instructions, or revise its manuscript.

The source corpus became available to this audit only after Stage 1. Its Woollard and MacAskill texts supply passages that the independent review could not fully obtain externally. In particular, Woollard leaves immediacy conditions open, and the MacAskill appendix contains the million-year probability sentence. This resolves access limitations for the system's next response; it neither changes the review's historical access tags nor overturns its local concerns about the inference from agency classifications to impersonal reasons. [Evidence: 02_corpus/sources/woollard-2015-doing.txt, pp. 17 and 207; macaskill-2022-wwotf.txt, PDF page marker 302.]

## 3. Production process and where the thesis was selected

| Phase | What actually happened | Advancement criterion and value |
|---|---|---|
| Opening, O1–O3 | Map, regional judgment, three acquisition batches, merge, and two additions of operator-supplied sources | Establish a live region and coverage of starting points. Eight calls; useful breadth, substantial acquisition cost. |
| First candidates, L1-01/L2-01 | Three proposals; advisor chose none | A compensation countercase defeated the leading claim; alternatives were hedged or insufficiently established. The return was used. |
| Second candidates, L1-02/L2-02 | Baseline/margin thesis, benefit-premium objection, and attributional-baseline objection | C1 selected; advisor added the benefit-premium extension and demanded a stronger corollary. |
| Targeted sources, L3 | Bostrom and Mogensen acquired; published Greaves–MacAskill and Quinn supplied; fresh source check | Target's latest statement and nearest antecedents assessed before planning. |
| Plan and plan check, L4–L5 | Plan criticized and revised | Several mathematical, interpretive, and scope errors caught; a corrected plan advanced without another plan check. |
| Draft and cold read, L6–L7 | Sonnet draft; fresh Opus report; Woollard acquisition | Reader found real magnitude and framing issues but also recommended an unjustified necessity thesis. |
| Rewrite and final check, L8 | Author adopted necessity framing; checker requested local repairs | New central weakness correctly triggered a fresh check, but that check missed the stronger conclusion's counterexample. |
| Clarity and verification | Forty first-pass notes; implementation; quote checks and render | Much clearer presentation and a usable anonymous PDF; original overclaim survived. |
| First outside review and response | Local revision recommended; source intake acquired Unruh 2025; advisor chose rewrite | Review's counterexamples accepted; necessity claim withdrawn, assumptions and illustrations separated. |
| Second-pass check, clarity, verification | Fresh check approved scoped result; 32 clarity notes; extra formatting retry; final verification | Principal defect repaired. Current manuscript supports submission with smaller local issues. |

The thesis was selected at **L2-02**, in work/choice-2.md. Alternatives were genuinely considered. work/choice.md's rejection of the first batch is philosophically productive, and should not be counted as avoidable waste merely because no manuscript came from it.

The selected insight is C1's difference between a cost proportional to P and a benefit proportional to Δ. That is new intellectual work within this run. The benefit-premium extension is another useful contribution. The first choice nevertheless says: **“This is a general-journal result only if the corollary and that consequence are made the centre. The bare inequality alone would be a note.”** This is the earliest clear pressure to make the result stronger than the baseline calculation warrants. [work/candidates-2.md, C1; work/choice-2.md, §2.]

Later stages did sometimes reconsider rather than merely preserve: L5 corrected the interpretation of the target's disjunction; the outside-review response abandoned the horizon-necessity thesis. But several intermediate repairs preserved the desired negative verdict by narrowing numerical descriptions or adding defenses without retesting the conclusion at its advertised strength.

## 4. Causes of the current manuscript's remaining weaknesses

These are local defects in a submission-worthy paper. Their architectural significance should not be inflated to justify wholesale redesign.

### A. The intended-benefit detour: an untested auxiliary inference

**First located occurrence:** work/plan-L4-01.md, step 10: a premium confined to intended benefits “applies at most to the Δ margin.” The revised plan retains this; the draft and final paper turn it into a categorical claim.

**Mechanism:** L5 primarily tests three central hinges. The auxiliary intention inference is neither separately defended nor tested. It then benefits from proximity to correct algebra: the reader can mistake an additional assumption about intention for another consequence of the model. No later record inspected supplies the missing bridge.

**Smallest intervention:** conditionalize or delete this optional detour. For future runs, the existing final checker should examine a small sample of categorical replies to alternatives, especially when they add a new account of intention, agency, or value outside the core model. This need not become an exhaustive sentence audit.

**Confidence:** high on the textual lineage; moderate on whether limited checker attention, inherited framing, or independent agreement explains the omission.

### B. Agency classification becomes exclusion of reasons

**First located explicit occurrence:** 09_final/round-1/final-L8-01.md, section 5. The draft's earlier horizon section does not contain the same explicit inference. The rewrite introduces the move from an agent's neither doing nor allowing remote outcomes to the disappearance of the benefit that recommends longtermist action. Its rewrite note identifies the new Woollard-based discussion as an unchecked central step.

**Mechanism:** a source's qualification about when “doing” and “allowing” apply is used as though it settled all reasons to promote remote good. The source check and final checks attend to whether a horizon is supplied, and to the quoted agency language, rather than this further normative inference. The current final check's I3 repeats that Woollard removes doing and allowing together but does not establish that impersonal reasons disappear.

**Smallest intervention:** retain the proposed sufficient mechanism and remove the claim that every other agency-based approach must fail. No positive theory of remote responsibility is needed.

**Confidence:** high about the missing inference and its survival; moderate about attributing it to a particular role boundary.

### C. A reasonably accurate source note becomes a misleading antecedent description

The Mogensen source note distinguishes justifying from requiring reasons and identifies the Non-Requiring View. work/source-check.md also records the role of justifying benefits. But its “Bearing” paragraph compresses this into asymmetric future bads threatening continuation. The first plan further compresses the point; the draft and final manuscript say the earlier argument turns on weighting bad lives above good ones. Clarity editing smooths that sentence rather than restoring its qualifications. [02_corpus/notes/mogensen-2019-staking.md, lines 10–14; work/source-check.md, Mogensen section; work/plan-L4-01.md, §5; work/clarity-notes-E-01.md; work/clarity-notes.md, note anchored to the Mogensen sentence.]

This was **not simply a missing-source failure**. The source was held and the main distinction was present in the notes. Final verification expressly says p. 27 supports the asymmetry claim. The weakness is testing whether a passage contains relevant words instead of whether it supports the manuscript's characterization of the earlier paper's argument. [09_final/verification-note.md, “Page claims checked.”]

**Smallest intervention:** check that paragraph against the original distinction and give the earlier paper a faithful one-sentence description. More corpus acquisition would not solve this case.

**Confidence:** high about the compression; moderate about whether the same mechanism recurs outside this run.

### D. Model assumptions and prominent scope

The first review identified the difference between expected choice-worthiness and constant additive weights. The response added an explicit diagnostic-model paragraph, a successful repair. The current final check recognized that the abstract still needed the model qualification and proposed it as an optional cheap fix. The delivered abstract does not include that phrase. [10_review/round-1/diagnosis.md, F4; work/rewrite-note.md; work/final-check-2.md, optional fix 1.]

The residual issue is small, but revealing: a check can recognize a scope improvement without ensuring that it survives final presentation. The records do **not** establish that a clarity editor removed an already-applied model clause; the saved pre-clarity abstract lacks it too. The narrower demonstrated problem is failure to carry the proposed qualification into the final abstract.

**Smallest intervention:** make the final claim comparison part of an existing edit/check, and distinguish an optional stylistic suggestion from a scope correction necessary to accurate advertising.

**Confidence:** high on the delivered text and recorded suggestion.

## 5. The larger failure already repaired

The earlier round's defect was more serious than the current local issues. L7 called the result “really a biconditional”; L8-01 explicitly adopted a claim that escape was possible only if the harm premium lapsed remotely. Yet the paper already admitted a nonempty full-weight escape band. The original final check validated the baseline cost, small margin, and possibility of a horizon, then endorsed necessity without testing exclusion of every non-horizon escape.

The first outside review supplied counterexamples; the response checked them, withdrew necessity, retained the central contribution, and produced the current paper. This was a successful correction rather than evidence that the research should have been abandoned. [work/reading.md, §2; work/rewrite-note-L8-01.md; work/final-check-L8-03.md; 10_review/round-1/diagnosis.md, F1; work/rewrite-note.md.]

A related failure is recorded for paper-4 in EVOLUTION.md's observation under v14.7: a model-specific cap was cleared as general. That establishes recurrence at the level of recorded diagnoses, not a new independent audit of paper-4.

The previous diagnosis marks a claim-strength intervention “adopt.” The present lean/roles/advisor.md still asks for at most three inferences supporting the abstract, without an explicit test of the full conclusion's quantifiers. A recorded adoption is not the same as deployment. Machine changes require the operator's decision, and STATE.md records outstanding machine notes; this is not evidence that a call disobeyed permission to change the machine.

## 6. Research methodology: what to retain and what to question

**Retain:**

- Source-grounded proposals and independent selection. The first rejection and second proposal generated the useful result.
- Focused primary-text checks at contested steps. L5 caught real interpretive and mathematical mistakes.
- Permission to stop or narrow, rather than automatically produce a manuscript.
- Cold reading without production history. It improved readability and identified missing literature, despite supplying one bad reframing.
- Independent external comparison, calibration, and a frozen review. The current paper's improvement demonstrates their value.
- Honest evidence limits. The source obligations and logs usually distinguish unread material from clearance.

**Question the objective, not only the number of checks.** The proposer, author, style file, and advisor repeatedly ask which named author must give something up. This is useful discipline against triviality, and the seed explicitly asks for a bold thesis. But it is too restrictive as the sole form of payoff: explanatory distinctions and conditional constraints can add publishable understanding without establishing that an opponent's complete position is false. In this run, the current narrower paper meets the calibration, whereas selection had treated a weaker fallback as merely a note.

This supports a controlled test of a broader significance question; it does not establish that boldness should be abandoned or that every sensitivity calculation is publishable. Keep the seed's ambition while requiring that the selected claim be supported before its more ambitious extension is promoted.

**The early literature search was broad but not complete at the relevant frontier.** Unruh 2025 arrived only after the outside review. The current acquisition rule reliably follows later statements by a target, but a contemporaneous reply by another author in the same volume is not necessarily caught. A small targeted neighbor check could help. A new exhaustive survey would repeat the broad acquisition that already consumed substantial effort. [work/intake-round-1.md; 10_review/round-1/diagnosis.md, F8; lean/roles/librarian.md, gather.]

## 7. Computational audit

### Measurement

I reconciled logs/calls.csv with corrections in logs/deviations.md and logs/run-log.md:

- IN-01: 121,597 tokens, 30 tools, 3.9 minutes.
- L8-06: 122,939 tokens, 13 tools, 3.3 minutes.

**Total: 36 calls, 4,670,095 processed tokens, 685 tool uses, and 154.4 summed call-minutes.** The pre-review production consumed 28 calls and 3,602,610 tokens. The response to the first review and preparation of the current version added eight calls and 1,067,485 tokens, about 22.9% of the recorded total.

These are completion-notice processed-token figures, including cached input. They are not fresh-input tokens, billable tokens, dollars, total orchestrator usage, or calendar elapsed time. Parallel acquisition and operator waits make summed call-minutes different from elapsed time. External reviewing costs are absent. No comparable price calculation is possible from this ledger.

| Work block | Calls | Processed tokens | Share |
|---|---:|---:|---:|
| Opening and initial corpus, O1–O3 | 8 | 1,062,977 | 22.8% |
| Candidate generation and selection | 4 | 606,317 | 13.0% |
| Targeted sources, source checks, and intake | 6 | 686,470 | 14.7% |
| Plan, revised plan, plan check, draft, cold read | 5 | 631,151 | 13.5% |
| Rewrites, final checks, and review response | 6 | 802,828 | 17.2% |
| Clarity editing | 5 | 625,516 | 13.4% |
| Verification | 2 | 254,836 | 5.5% |

Opus accounts for 21 calls and 2,801,677 processed tokens; Sonnet for 15 calls and 1,868,418. The run remains below the orchestrator's under-10M aspiration, although “about a dozen calls” understates a new lineage with acquisition, returns, editing, and review response.

### Value and diminishing returns

**High-value expensive reasoning:** rejecting the first candidates; producing and selecting the baseline/margin argument; testing the plan; reassessing the actual surviving result after outside review. Do not cheapen these first.

**High-cost block worth testing:** initial plus targeted source work totals 1,749,447 tokens, 37.5%. Some creates a reusable corpus, and acquired material also enabled rejection of bad proposals. It is not all waste. But broad coverage before a promising lead, repeated source offers, merge work, and later targeted acquisition create an opportunity for staged retrieval.

**Demonstrated avoidable call:** E-05 consumed 89,065 tokens to explain a paragraph split already present. The paper was not changed. That is about 1.9% of total recorded processing, caused by a deterministic false alarm. [logs/calls.csv; logs/deviations.md; work/clarity-response-E-04.md; final-E-04.md/final-E-05.md.]

**Repeated polish:** five clarity calls cost 625,516 tokens. The main edits delivered real readability gains, so eliminating clarity is unsupported. The next experiment should distinguish a fresh global edit from a limited check of changed passages after local revision.

**Do not call all later revision waste.** The extra 1.067M repaired a real failure and added a relevant source. Some might have been avoided by better early claim testing, but the ledger cannot identify that counterfactual saving or justify claiming the entire amount was avoidable.

## 8. Deterministic failures and redundant work

**Word counter:** system/tools/wordcount.py, line 30, treats `<[^>]+>` as an HTML tag. In the current manuscript it matches two spans containing 60 and 1,805 whitespace words. The second span crosses much of the paper. The verifier reports the tool's total as 3,560 and its workaround count as 5,471. The script also drops an entire title or abstract containing “<” at lines 104–105. This is a clear parser defect, not a philosophical uncertainty.

The rewrite, clarity response, verifier, event log, and review request all dealt with this one defect; the review metadata retained the undercount. The manuscript itself stayed within the corrected limit. Repair the shared counter rather than require agents to repeat scratch substitutions. [work/rewrite-note.md; work/clarity-response-E-04.md; 09_final/verification-note.md; logs/deviations.md.]

**Clarity checker:** the notes request a paragraph break while retaining the words. system/tools/clarity_check.py, lines 122–132, expects literal replacement text or disappearance of the anchor. It treats the editor's instruction as text to find, and normalization cannot verify the requested paragraph boundary. The orchestrator's section 4e automatically escalates that failure to another author call.

**Documentation:** the stale audit map and run README still describe older runs or architecture. Fix the misleading pointer by deriving the current run from STATE.md, not by adding another maintained manifest. This is a repeated low-cost maintenance problem.

**Logging:** the two usage corrections are honestly recorded, but totals require joining free-text deviations to missing CSV values. Record completion usage after it arrives, or update the existing row with an auditable correction. Do not spend a model call reconciling figures that a small script can join.

## 9. Prioritized, testable recommendations

### R1 — Test the whole advertised claim in the existing final check

- **Observed problem:** correct component calculations accompanied an unproved necessity conclusion; smaller categorical auxiliary claims survive in the current paper.
- **Hypothesized cause:** decomposition checks support for ingredients but loses quantifier, parameter, and scope commitments in their advertised combination.
- **Evidence:** work/final-check-L8-03.md versus the original abstract; work/reading.md's “biconditional”; round-1 diagnosis F1; EVOLUTION.md's paper-4 observation.
- **Proposed change:** replace generic extra checking with a short obligation in the existing final check: state the strongest literal conclusion, its quantifiers and assumptions; attempt one counterexample in the paper's own permitted parameter space; then test whether the proposed repair changes that conclusion. For non-formal arguments, use the nearest relevant alternative reading instead of numerical search.
- **Expected benefit:** prevent the demonstrated class of overclaims without another standing reviewer.
- **Potential cost:** a little checker attention; mechanical counterexample hunting can misfire when assumptions are misunderstood.
- **Confidence:** high that the old failure needs this test; moderate about performance across philosophical genres.
- **Evaluation:** replay the pre-review abstract and the narrowed current abstract blind. The new instruction should reject the former's necessity claim and accept the latter's scoped result, without manufacturing a structural defect. This is the earlier R1 in revised operational form; implement the pending decision rather than commission another generic audit.

### R2 — Select the best supported payoff separately from its ambitious extension

- **Observed problem:** choice-2 made general-journal significance depend on a stronger corollary, although the eventual narrower result meets the supplied calibration.
- **Hypothesized cause:** an exclusive named-opponent-defeat test favors stronger negative framing over explanatory progress.
- **Evidence:** work/choice-2.md, §2; lean/roles/proposer.md; lean/roles/author.md, plan item 2; lean/STYLE.md's standard.
- **Proposed change:** in the existing choice file, distinguish the best supported result from a possible stronger extension, and judge each against the nearest antecedent. Allow an illuminating constraint or explanatory alternative as payoff when its substantive consequences are specified.
- **Expected benefit:** less pressure to preserve an overstrong thesis through defensive additions.
- **Potential cost:** weaker projects could pass if “insight” becomes an excuse for small stakes.
- **Confidence:** high about the instruction and this lineage; moderate about general causation.
- **Evaluation:** paired selection judgments on a few existing candidate packets, with later blind judgments of significance. Test first; keep a demanding significance threshold.

### R3 — Check the context of decisive paraphrases within existing verification

- **Observed problem:** the Mogensen note records the relevant distinction, but the manuscript mischaracterizes the earlier argument.
- **Hypothesized cause:** quotation and locator verification does not reliably test contextual entailment of the surrounding paraphrase.
- **Evidence:** the source note, source-check bearing paragraph, plan §5, the clarity note on the Mogensen sentence, and verification-note's p. 27 clearance.
- **Proposed change:** have the existing source/argument checker select at most five decisive paraphrases or exclusion claims and compare each with its source paragraph plus the source's conclusion. Replace some duplicate quote attention; add no new role or separate report.
- **Expected benefit:** preserve qualifications through note-to-plan-to-prose compression.
- **Potential cost:** several focused source reads; weaker automation than literal matching.
- **Confidence:** high for the observed failure; moderate for the best allocation between advisor and verifier.
- **Evaluation:** test on the actual Mogensen sentence, an accurate revised sentence, and three control paraphrases. Require correct contextual discrimination, not more quotations.

### R4 — Repair the counter and classify formatting checks before escalation

- **Observed problem:** massive mathematical undercount and the no-change E-05 retry.
- **Hypothesized cause:** regex-based treatment of semantic text as HTML, and literal-text verification of nonliteral edit operations.
- **Evidence:** wordcount.py lines 30 and 104–105; clarity_check.py lines 122–132; deviations and E-05 usage.
- **Proposed change:** protect mathematical content before removing genuine markup; stop dropping titles/abstracts merely for containing “<”. Verify paragraph operations as paragraph boundaries. Route schema/checker faults to a deterministic diagnosis instead of automatically asking an author to rewrite.
- **Expected benefit:** reliable length gates and immediate removal of a demonstrated unnecessary strong call.
- **Potential cost:** small tool maintenance; no philosophical capability removed.
- **Confidence:** high.
- **Evaluation:** regression cases for inequalities, genuine HTML, mathematical abstracts, unchanged wording with a paragraph split, real replacement omissions, and deletions. Current paper's count should reconcile with the documented workaround without changing the paper. Immediate repair is warranted.

### R5 — Test staged acquisition and a narrow neighboring-literature search

- **Observed problem:** acquisition is the largest combined cost block, yet Unruh 2025 was missing until review.
- **Hypothesized cause:** coverage of broad starting points is front-loaded, while same-debate work by non-target authors is less systematically revisited.
- **Evidence:** O3 and L3 ledger; corpus-index; intake-round-1; librarian gather's successor rule.
- **Proposed change:** retain the operator-requested reply survey, acquire a small diverse initial set, and defer the remainder until two promising mechanisms need it. At selection, perform a bounded search of the focal publication's neighboring chapters/replies.
- **Expected benefit:** earlier consequential literature at lower acquisition and operator cost.
- **Potential cost:** missed cross-connections, premature narrowing, and losing sources that would have exposed a bad candidate.
- **Confidence:** moderate on opportunity; low-to-moderate on net savings.
- **Evaluation:** a matched-corpus acquisition trial on proposal notes, including rejected candidates; measure useful countercases found, pivotal sources missed, retrieval attempts, and processed tokens. Do not implement by simply cutting the corpus quota.

### R6 — Make post-revision clarity conditional, and preserve content constraints

- **Observed problem:** global clarity passes recur after substantive/local rewriting, and optional scope suggestions can remain unimplemented.
- **Hypothesized cause:** every revision triggers roughly the same edit workflow, without separating changed passages from unchanged prose.
- **Evidence:** E-01/E-02 and E-03/E-04; final-check-2 optional scope fix; orchestrator §4e.
- **Proposed change:** preserve one full fresh clarity read. After a bounded local revision, test a focused changed-passage read and implementation in an existing call. Reuse the available polish comparison machinery, or a simple aligned diff, to flag changes in qualification; do not add another permanent semantic reviewer.
- **Expected benefit:** less repeated editing and clearer accountability for scope.
- **Potential cost:** global coherence problems may escape a local pass; cheaper implementation may alter content.
- **Confidence:** moderate; test before replacement.
- **Evaluation:** blind readability and content-fidelity comparison of the actual post-review version under full and focused passes. A lower token count alone is not success.

### R7 — Remove stale pointers and normalize usage corrections

- **Observed problem:** two audit rounds encountered the historical run pointer; ledger totals require free-text reconciliation.
- **Hypothesized cause:** manually maintained navigation examples and early logging before completion.
- **Evidence:** audit map versus STATE.md; first architecture report §2; IN-01/L8-06 deviations.
- **Proposed change:** remove the static “which run” example or render it from current state; update corrected usage in the existing ledger with provenance. Keep the event history.
- **Expected benefit:** reproducible audits and accurate cheap totals.
- **Potential cost:** small tooling/document maintenance; no extra model calls.
- **Confidence:** high.
- **Evaluation:** resolve this packet's run and compute 4,670,095 tokens from canonical records without reading a narrative deviation manually.

## 10. Proposal A: repair the present architecture

Keep selection, source checks, a plan, independent criticism, whole drafting, one substantive rewrite, one fresh clarity pass, verification, and independent outside review.

Implement R1 and R4 first; incorporate R3 by reallocating existing verification effort. Remove automatic author retries for checker-schema faults. Fix the stale map and usage rows as ordinary maintenance. Test R2, R5, and R6 separately, not as a bundled new version.

A narrowing change should reduce the claim and delete unnecessary defenses. It should not automatically reopen the whole project. Conversely, a new central inference still warrants fresh scrutiny. The current one-return rule is acceptable as a compute stop, provided a failed run produces a useful brief rather than a forced paper.

Expected benefit: fewer invalid headline claims and fewer mechanical loops, with little added instruction or call overhead. The immediate saving demonstrated here is the E-05 class of retry; broader savings remain unmeasured. Main risk: marginally longer checks, unless replaced checks are actually removed.

This is my preferred production proposal now.

## 11. Proposal B: a research-note-first simplification

Test a substantially different baseline on the same held sources:

1. A researcher writes a short argument note with two or three mechanisms, the best supported claim, nearest source passages, and an explicit countercase. No full outline.
2. A fresh critic selects or rejects the strongest actual result, testing significance, priority, and its decisive inference.
3. A librarian resolves only the source obligations that can change that decision.
4. A strong author writes a whole draft directly from the approved argument note.
5. A fresh reader judges the whole paper; one bounded author revision follows.
6. One clarity read/edit and one mechanical verification/render finish it; then the existing independent review.

Drop separate region approval when the operator has supplied a specific live debate; drop broad corpus coverage before a lead; merge choice and plan approval into the argument-note judgment; drop the separate cheap first draft followed by a wholesale strong rewrite. Preserve a blind reader and source access.

This is not a license to skip the requested initial reply survey or relevant counter-literature. New-topic mapping and acquisition still have to be counted. Nor does a shorter argument note guarantee enough exploration.

Expected benefit: fewer handoffs, less repeated context processing, and insight established before most prose expenditure. Risks: weaker exploration, less division of labor, one author's blind spots, and later discovery that sources defeat a nearly written paper. An initial target of roughly 8–12 calls excluding genuinely new bulk acquisition is an experimental design goal, not a measured prediction or guaranteed token saving.

## 12. Modest-cost experiments and stopping rules

1. **First, replay claim-strength checks.** Use the original paper-5 abstract, the current scoped version, the recorded paper-4 cap case, and at least one valid controversial argument. Compare old and R1 instructions blind. Score detected scope errors and false holds on valid conditional contributions. Small notes suffice.
2. **Test contextual paraphrase verification.** Use the real Mogensen passage and controls from other run sources. Compare current quote/page verification with R3's small contextual sample. Measure accuracy and extra processing, not verbosity.
3. **Repair and test deterministic tools without drafting a paper.** R4's fixtures and a packet-resolution/ledger-total check for R7 cost virtually no research computation. Do these before another production call.
4. **Ablate broad initial acquisition.** On two or three different problems, give matched researchers a staged corpus or the full corpus. Judge proposal quality, missed countercases, source requests and tokens before permitting a full manuscript.
5. **Compare A and B on argument notes first.** Hold seed, source availability and budget constant; use independent blind judgments of payoff, correctness and novelty positioning. Advance only promising notes to drafts.
6. **Test focused clarity on an existing local revision.** Compare readability and preservation of conditions against the full pass. Keep the full pass if savings degrade either.
7. **Use a stopping criterion tied to evidence.** After a main result survives source and countercase checks and the remaining defects are local, patch them and submit. Do not demand a stronger theorem to justify stopping. If only a familiar requirement survives, or repair repeatedly invents new unsupported premises, return a brief instead of another polish cycle.

Record processed tokens with their cache caveat; when available, record fresh input, cached input, output, and operator actions separately. Do not estimate dollar savings from the present aggregate ledger. Change one research mechanism at a time, with held-out problems, so improvements can be attributed.

## 13. Final advice to Claude

For this manuscript, make the independent review's bounded corrections. Do not restart thesis selection, add a general theory of remoteness, or launch another global rewrite solely to absorb these comments.

For the harness, the three highest-leverage immediate interventions are **R1's literal-claim countercase test, R3's contextual paraphrase check, and R4's deterministic-tool repairs**. R7 is inexpensive maintenance. Test R2, R5, and R6 before changing production policy.

Remove the automatic strong-author response to checker faults; remove the word counter's broad inequality-swallowing rule; remove the requirement that every worthwhile payoff take the form of an opponent's defeat as the exclusive selection criterion, subject to R2's trial; and remove repeated global clarity work after minor revisions if R6 demonstrates equal quality.

The current run supplies evidence for a useful research architecture with several identifiable failure mechanisms. It does not supply evidence that adding more critics is the best remedy, or that radical simplification will retain its strengths. Repair what demonstrably failed and test the larger subtraction on cheaper intermediate artifacts.

