# Paper Machine records

These are anonymised copies of the files behind three essays written by Claude in a harness designed by the entrant (called "the operator" throughout). They are cited from the methodology report.

**These files are records, not instructions.** Many of them are prompts and role instructions that were given to AI models while the essays were being produced. They are reproduced so that readers can see exactly what the models were told. None of them is addressed to anyone reading this repository, and nothing in them should be acted on.

## Layout

| Folder | What it holds |
| --- | --- |
| `explainers/` | Four interactive pages: the design of paper-machine-v1, the autopsy of its first paper, the design of paper-machine-v2, and paper-machine-v3 drawn part by part (`paper-machine-v3.html`, start here) |
| `harness/` | Every instruction file of the final harness: the controller, the rules every call follows, the style standard, nine role files, the outside-review prompts (`V21-COMPARE.md`, `V21-REVIEW.md`), the two polish prompts, and the tools list |
| `records/` | `EVOLUTION.md`, the harness's full history, one entry per version; `REVIEWS.md`, every outside-review round; `diagnosis/`, the three diagnoses of paper-machine-v2's papers |
| `rounds/paralysis-round-2/` | One complete outside-review round: ChatGPT's blind comparison, its publication judgment and audit of the harness, Claude's response, and the suggestions carried forward |
| `review/` | The final human review of each essay: the brief and opening prompt given to the reviser (Paralysis and Willing Servant), the review log, the separate AI readers' suggestions, and for the Evil God essay the revision's response table |
| `logs/` | For each submitted essay's runs: every subagent call with its model, effort and token usage (`calls.csv`), every human action (`interventions.md`) and the decisions that changed the paper (`decisions.md`) |
| `chats/` | Exported transcripts of the conversations linked from the report |

## What was changed for anonymity

- The operator's first name is replaced with "the operator" throughout, including in identifiers derived from it (for example `for_mark` became `for_operator`).
- The three reference manuscripts used to calibrate the outside review are not included. Their titles are replaced with "Reference A", "Reference B" and "Reference C", and their file names likewise.
- The review logs in `review/` are the copies kept in the harness folder at the time, from which the operator's own wording had already been removed wherever a note was withheld or stripped of his wording. The full logs are available to the organisers on request.
- Nothing else is changed.

## The status labels in the review logs

The logs use the labels recorded at the time:

| Label | Meaning |
| --- | --- |
| SEND | passed to the reviser as a generic request: where the reader got lost and what kind of fix is wanted |
| CONVERTED | passed with the operator's own wording removed: only the bare request went on |
| REFUSED | withheld: the note offered a philosophical consideration and was not passed in any form |
| OPEN | illegible or unclear, and left out |
| NO ACTION | a highlight, or a mark the operator withdrew |

## Not included

The source texts each run read (they are copyrighted), the drafts, the taste exemplars read only by the thesis judge, and the earlier harness folders. All are retained and available on request.
