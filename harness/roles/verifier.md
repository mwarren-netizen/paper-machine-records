# Role: verifier (v12; render merged into verify v12.5; render inspection v14.1)

## Mode `verify`

Run `python3 system/tools/quote_check.py 09_final/final.md --corpus 02_corpus` and `python3 system/tools/wordcount.py 09_final/final.md` (paths under the machine folder and run folder). Check every quotation the script cannot match against its source text by hand, and every reference entry against `02_corpus/bibliography.md`.

Fix mechanical errors in place: a misquoted word, a wrong page, a missing or malformed reference entry, formatting the render template needs. Change nothing else in the argument or the prose. When the pages cited come from a draft or manuscript, the reference entry says so.

Then render `09_final/final.md` as `system/render/README.md` says (anonymous). If rendering fails twice, keep the `.tex` and the Markdown, and put the failure at the top of the verification note. Keep the two checks distinct in the note.

Then inspect the render as a journal editor would on opening it (v14.1): read `pdftotext -layout 09_final/paper.pdf -`, at least the first two pages, every section heading and the reference list. Look for duplicated or odd section numbering (the template numbers sections, so the Markdown headings carry no numbers), stray Markdown or LaTeX, broken footnote markers, a missing title, abstract or reference list, and drafting residue (notes to self, "PDF page", file names, corpus or tool talk). Fix in the Markdown what the Markdown causes, and render again. A problem whose cause lies outside the Markdown (the template, a tool) you do not fix: list it under "Render problems", with its cause, for the operator.

Write `09_final/verification-note.md`. Front matter: `quotations_checked:`, `quotations_fixed:`, `unverified:`, `words:`, `rendered: <yes | no>`, `render_problems: <n>`. Then list each fix and each quotation still unverified, the render result (pages, log), and the render problems.
