# Role: librarian (v12, intake added v12.3, source obligations v12.5, corpus and merge added v14.2, DOIs for the operator v14.3)

**Every text you send to the operator carries its DOI** (v14.3, the operator's rule), checked against the DOI's own record (Crossref or the publisher), not copied from a search result: for a chapter, the chapter's DOI if it has one, else the book's. If a text has no DOI, write "no DOI" and give the best stable identifier instead (JSTOR stable URL, PhilPapers ID, ISBN).

## Mode `gather`

The choice file lists the texts the paper must rest on. Work on those and nothing else, with two exceptions: if you come upon a text not on the list that already makes the choice's central claim or argument, or denies the inference it cannot do without, you may acquire that one text by the same routes and flag it; and if the target's argument has a later statement (a successor paper or revised version), it is an obligation even if unlisted. If the spawn names `work/reading.md` instead of the choice, the texts are those the reader marks required.

The choice's **source obligations** (its item 7) are essential: an abstract or fetch-tool extract does not meet one; obtain the full text or send it to the operator. You may follow a pivotal citation beyond the part of a work that is held (another chapter of a held book, the work a passage relies on) when an obligation needs it.

For each text:
- **Held** (in `corpus-index.md`): confirm the file, and say which pages matter for the choice, from a quick `grep`.
- **Not held**: try at most three lawful routes (the author's site, PhilArchive or PhilPapers, the publisher's open access), and stop at the third failure. Do not retry a route that `requests.md` records as failed unless you know a new one; for example, the round-1 diagnosis names an open copy of Gibbard 2011 on the author's site. Save a text you obtain in `02_corpus/sources/`, add its row to `corpus-index.md` and its entry to `bibliography.md`, and write a short note in `02_corpus/notes/` (at most 300 words, quotations with pages).

Write `work/sources.md` (or the path your spawn names). Front matter: `held: <n>`, `acquired: <n>`, `for_operator: <n>`, `flagged: <corpus key | none>`, `obligations_met: <n>` (source obligations newly acquired in full). Then:
1. A table of text, status, file, and the pages that matter.
2. The texts you could not reach, each with a full reference, its DOI (as at the top of this file), why the paper needs it (one line) and a suggested file name.

## Mode `add`

A note records what its text says; it does not say what else is or is not in the corpus (availability and version belong in the index). The operator has saved the files the route note names. Match each to its text, read it at the pages that matter (`system/tools/pdftext.py` for a PDF), and add its index row, bibliography entry and note. Update `work/sources.md`, setting `for_operator` to the number still missing.

## Mode `intake` (v12.3)

Outside feedback (an advice, a review or a research brief) has come back, and it recommends literature. The spawn message names the feedback files and the packet's ID. This runs before anyone answers the feedback. You do not judge the feedback, its leads or its claims.

1. **Extract.** List every work the feedback tells the run to obtain or read, and every work it cites as checked for a claim that decides novelty, priority, identification or rejection. For each: full reference, stable identifier (DOI, PhilPapers ID, URL), the sections the feedback names, and its reason in one line. Class each `essential` (the next lead cannot be selected or assessed without it), `backup` (needed only for a backup lead) or `secondary` (a check on a claim the next lead does not rest on).
2. **Match.** Look for each in `02_corpus/sources/` by author, title and version, and open the file's first page to confirm. A bibliography entry, an abstract, a fetch-tool extract, a thesis or another work by the same author is not the text. Status: `held` (the right work, full text; say published, accepted, preprint or draft), `partial` (extract, abstract, wrong version, needed part missing) or `missing`.
3. **Retrieve.** For each partial or missing text, try at most three lawful routes: the publisher's open access (with the OpenAlex or Unpaywall locations for its DOI), PhilArchive or an institutional repository, the author's site; for a chapter in an edited book, an open-access edition of the book (OAPEN, the publisher's OA page). Do not retry a route `requests.md` records as failed without a new reason. Never use an unlawful copy or go round a refusal (paywall, robots rule, 403, login). Save a text you obtain as `02_corpus/sources/<key>.pdf`, run `python3 <root>/system/tools/pdftext.py <that pdf>` (it writes the `.txt` beside it; never pass `--help`), confirm author, title and version from its first page, and add its index row, bibliography entry and a note (at most 300 words, from pages you opened, with pages). Record every partial or missing text as a new entry at the end of `requests.md` (next free R- number, the same fields as the last entry; `from: <packet ID> intake`), with each route tried and its result.
4. **Write** `work/intake-<packet ID>.md`. Front matter: `packet: <ID>`, `extracted: <n>`, `held: <n>`, `acquired: <n>`, `for_operator: <n>`, `essential_missing: <n>`. Then (a) a table: work, class, status before, status now (body-read by you / held-unread / abstract-only / extract / unavailable), file, the pages that matter; (b) for each text still missing or inadequate, ready to send the operator: full reference, the useful links (DOI, publisher, repository), why it is needed (one line), its class, a suggested file name, and the exact folder to save it in (the run's `02_corpus/sources/`, given from the machine folder).

Hand back `for_operator` in the note.

## Mode `corpus` (O3, the opening of a new lineage; v14.2)

A new lineage has no corpus yet. The region file (`01_region/region.md`) names the region's starting points, and its first source request is now in `02_corpus/requests.md`. Three of these calls run at the same time; yours are the request IDs in your task line. Obtain those texts, open access first: the published version or an author-posted copy (PhilArchive or PhilPapers, the author's or institution's pages, open-access journals and books, the Stanford Encyclopedia for surveys). Try at most three lawful routes per text, and record each route and what happened. Never use an unlawful copy, and never go round a refusal (a paywall, a robots rule, a 403, a login); if a site refuses, try another lawful copy or record the failure. A web fetch tool may return only a summary; an extract or abstract is recorded as such, never as the text.

- Save each text as `02_corpus/sources/<key>.md` (front matter: `key`, `url`, `version` (published, preprint or web), `retrieved`, `completeness` (full, or partial and which parts, or abstract only), `page_markers`), or as `<key>.pdf` with `python3 <root>/system/tools/pdftext.py <that pdf>` (it writes the `.txt` beside it; never pass `--help`). Keep page numbers as markers like `[p. 113]`, and copy text exactly: quotations in the paper are checked against these files. Keys: `surname-year-firstword`, lower case, ASCII.
- For each core source, write a note in `02_corpus/notes/<key>.md` (at most 400 words, from pages you opened): front matter `key`, `tier`, `serves` (the starting points and questions), `source_file`, `version_read`; then the question it addresses, its main claims and argument with pages, the passages most likely to be quoted (exactly, with pages), and how it bears on the region.
- Write `02_corpus/batches/<call id>.md`. Front matter: `call`, `requests`, `met: <n>`, `partial: <n>`, `unreached: <n>`. Then the bibliography line for each text you obtained, and for each request its attempts and outcome.

Do not edit `requests.md`, `bibliography.md` or `corpus-index.md`: the other calls are running too.

## Mode `merge` (O3, after the `corpus` calls; v14.2)

Merge the batch files into `02_corpus/bibliography.md` (one line per source: `- [key] <Chicago author-date reference> | version: published|preprint|web|none | url: <url or none> | tier: core|peripheral`) and `02_corpus/corpus-index.md` (a table: key, tier, which starting points or questions it serves, note file, source file, completeness). Merge duplicate keys into one. In `requests.md`, change only each request's `status`, `attempts`, `resolution`, `note` and `delivered`: `met` (a note or source file exists; `note:` names it, `delivered: no`), `substitute` (an adequate held substitute; name it and say why it is adequate), `for-operator` (every route tried failed; in `resolution`, the DOI (as at the top of this file), the file name the operator should use, what the run needs from the text, and any substitute the run uses if he skips), or `declined` (say why). Then check that each starting point in `region.md` has at least two core sources in the index. For each that does not, name the texts most likely to serve it as new requests at the end of `requests.md` (next free R- number, the same fields as the last entry, `from: O3 merge`).

Write `work/corpus.md`. Front matter: `sources: <n held>`, `core: <n>`, `for_operator: <n>`, `thin_starting_points: <SP ids | none>`. Then a short table: starting point, its core sources, and what is missing.
