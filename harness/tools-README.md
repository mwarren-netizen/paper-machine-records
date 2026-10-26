# Tools

Small Python scripts (standard library only; Python 3.8 or later) for the mechanical parts of a run. The orchestrator and some roles run them; nothing philosophical happens here. Each prints its usage with `--help`. Run them as `python3 <root>/system/tools/<script>.py`, where `<root>` is the machine folder. None of them deletes anything.

| Script | Step | What it does |
|---|---|---|
| `new_run.py` | V00 | creates `runs/<run_id>/` from `runs/_template/` |
| `log.py` | throughout | the only writer of the logs: calls, events, the operator's actions, decisions, deviations |
| `requests.py` | throughout | the source-request queue: harvest REQ lines, split batches, deliver notes to owners, list |
| `setup_voices.py` | V03 | draws one disposition per family at random, pairs them with starting points, opens the notebooks |
| `new_papers.py` | V07 | creates the two paper folders and the authors' notebooks |
| `freeze.py` | V11, V14 | freezes the paper project and the outline (read-only, dated) |
| `draw.py` | V12 | deals four disparate strategy menus |
| `budget_check.py` | V12, V14, V15 | outline and unit budget arithmetic against the ceiling |
| `draft.py` | V16 to V18 | appends units to the rolling draft; assembles the paper with its reference list; extracts the front door for the desk-reject reader |
| `blind.py` | V16 | shuffled, label-free copies of a unit's three passes for the selectors; unblinds the choice (added 2026-10-10) |
| `packet.py` | V16 | per-unit reading packets for the passes and the selection, in place of the whole section spec, outline and index (added 2026-10-13, v9.0) |
| `wordcount.py` | V16 to V20 | the conservative word count, with a breakdown; v15.0: math and bare `<` no longer read as markup, `--selftest` runs the regression cases |
| `clarity_check.py` | clarity edit, abstract pass (v14.1) | checks that the editor's notes were taken up; v15.0: a note that only splits a paragraph passes when a paragraph of the paper begins at its anchor |
| `pdftext.py` | corpus | page-marked text from a PDF the operator supplies |
| `quote_check.py` | V20 | finds every quotation in the corpus, with its page |
| `methodology.py` | V20 | compiles the run's methodology dossier from its logs |

The rendering script is `system/render/render.sh`.

Added 2026-10-12 for the outside review loop (V20 to V22; protected, `system/PROTECTED.md`):

| Script | Step | What it does |
|---|---|---|
| `review.py` | V20 to V22 | puts the paper in `REVIEW/` for the outside reviewer, files the review in the round folder, adds the round to `REVIEWS.md` |
| `polish.py` | final polishes (v14.7; v15.1) | `name`: a paper's file name by title and stage; `render`: a polish to `<title> (<stage>).tex/.pdf` with a copy in `PAPERS/`; `shelf`: names each candidate's `09_final` PDF, renders pending polishes, writes `PAPERS/README.md`; `file-reply`: files a pasted polish; `adopt`, `check` (line or structure rules), `revert`: after the operator chooses a polish; `compare`, `count` (everything but the references; limit 6,000) |
| `branch_run.py` | V22 | a new run folder that keeps everything made before a step, for a rerun (tier 2 and 3) |
| `evolution.py` | V22 | snapshots the machine, gates the machinist's changes (protected files and blocks, size ceilings, oscillation, the `EVOLUTION.md` entry), diffs and restores |
