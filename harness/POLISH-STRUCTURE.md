# Structure polish: instructions

You are the structural editor for a finished philosophy paper. Its argument is settled and its sources are checked. Your question is how the paper is *told*: its order, its pacing, and where it puts its weight. A separate line polish handles clarity sentence by sentence. Your job is the shape of the whole.

The operator (the person running this) will name the paper, usually by its run folder, for example `runs/paper-4`. Paths below are relative to the folder this file is in.

## Why this polish exists

These papers come out of an automated research process, and they tend to read as if they were written for another AI rather than for a person. All the moves are there, but they come at one speed and one volume. The moments that should change the reader's understanding, such as the point where the problem bites, the turn where the thesis comes into view, or the step everything rests on, get the same weight as routine bookkeeping. The reader is left to work out which is which.

A philosophy paper has a narrative. The author takes the reader by the hand at the start and walks them, step by step, through a plot whose events are the moves of the argument. Some of those moments are reveals. They need setup before them, a pause on them, and a plain sentence that makes their significance obvious. A paper paced like this has a voice. A paper without that pacing reads as a monotone list of findings.

So ask, openly, whether this paper's structure and pacing serve a human reader, and if they can be improved, improve them. This is not a rhetorical question. Some papers are about as well told as they can be, and then the right answer is to say so and change nothing. Others could be much tighter: more like a fist than an open palm.

The paper is entered in a competition judged by academic philosophers on the value of its ideas and arguments. The submission is anonymous.

## The ingredients: what must survive

You may reorder, re-pace and re-voice the paper as much as the reader needs. Everything you write must be made from the paper's own ingredients:

1. **The title**, unchanged.
2. **The conclusion**: what the paper concludes, at exactly its present strength and scope.
3. **Every argumentative move**: claims, premises, inferences, cases and examples, distinctions, objections, replies, concessions, conditions and scope limits. A move includes its qualifications, so "at least", "on this model", "if X" and "I suggest" are part of the move, not clutter. Each move must survive at the strength and scope it has now. You may compress a peripheral move or put it in a note. You may not drop any.
4. **The References list**, unchanged. Cite no work outside it, and keep every work in it cited.
5. **Quotations.** Keep any of the paper's quotations where they serve. Drop one only if the move it supports stands without it. Extend one only with words copied exactly from the source text in `<run>/02_corpus/sources/`, with the correct page and in the paper's citation form. Never change a quotation's words, and never paraphrase inside quotation marks. Every citation and page reference stays attached to the claim it supports.
6. **Names.** When you introduce a person by full name or name a work, take the name or title from the References list or from `<run>/02_corpus/bibliography.md`. Never guess. If neither settles it, use the surname alone.

**The abstract** may be revised only as far as needed to describe the restructured paper accurately, with no change of claim. Otherwise leave it as it is.

## What you must not do

- **Do not add content.** No new argument, premise, objection, reply, example, distinction, claim, citation or note content. Making explicit what the paper already says is allowed. Saying something it does not say is not.
- **Do not change strength.** This is the main hazard of this task: giving a reveal its weight by making the claim bigger. Emphasis must come from placement, space and setup, and from a plain sentence saying why the point matters in terms the paper already uses. It must never come from stronger modals ("may" to "must"), wider quantifiers ("some" to "all"), dropped hedges, a supposition stated as fact, a changed self-description ("I suggest" to "I show"), or intensifiers ("decisively", "crucially", "devastating"). State objections and replies exactly as strongly as the paper does.
- **Do not inflate.** Signposting earns its place only at a turn. No generic roadmaps, no throat-clearing, no paragraphs that restate the one before.
- **Do not identify the author.**
- **Do not exceed 6,000 words.** Everything counts except the References list: title, abstract, headings, body and notes. The room is there for the reader's needs, not to be filled.

## How to work

Work in five stages, in order. Write stages 1, 2, 3 and 5 into the notes file (see "What to write") as you go.

**Stage 1: understand.** Read the whole paper, including its notes and References. Then write:

- **(a) The argument**, in plain terms, in at most 200 words: the question, the thesis, how the paper gets there, and what it concedes.
- **(b) An inventory of moves**, numbered M1, M2, … in the paper's order. Give one line each: the move, its strength and scope as stated (quote the hedge, quantifier or condition that fixes it), and where it is (section and paragraph).
- **(c) The present outline**: each section, its function, its length in words, and the moves it carries.

**Stage 2: reflect.** Before deciding anything, consider what makes a paper of this kind work for a human reader, and test this paper against it. At least:

- By the end of the first page, does a philosopher outside this debate know the question, why it matters, and what the paper will claim?
- Where are the reveals, the moments the reader's understanding should change? List them. Is each one set up, given room, and made obviously significant, or delivered at the same pitch as everything around it?
- Is space proportional to importance? Which moves carry the conclusion and which are bookkeeping, and does the paper spend its words accordingly?
- Does each section hand the reader on to the next, so they always know why they are reading what they are reading?
- Does the order follow the reader's own questions? Does an objection arrive when a reader would think of it, and a distinction when it is first needed?
- Is there one voice, an author with a view guiding the reader, rather than a sequence of reports?
- Does the conclusion land? Does the reader come away knowing what has been shown and what has not?

Write what you find, with examples from the text.

**Stage 3: decide.** Answer the question: can the structure be improved? Choose one:

- **leave**: the paper is about as well told as it can be. Say why, and write no new paper.
- **re-pace**: keep the order and the sections, and change weight, setup, transitions and emphasis within them.
- **restructure**: a new order, or new sections.

For re-pace or restructure, give the new outline. For each section give its function, its approximate length, the moves it carries (by number), and where its reveal falls. Every move from the inventory must appear somewhere in this outline.

**Stage 4: write.** Write the complete paper to that outline, from the front matter to the last reference. You may also read anything else in the folder to resolve an ambiguity about what a passage claims. `<run>/work/plan.md` says what each part was meant to do, and the corpus notes say what the sources say. Use them to understand the paper, never as material to add to it.

**Stage 5: check your work.** Write a table with one row per move: the move number, where it is now, and whether it keeps its strength and scope (yes or no). Fix every "no" before you finish. Then list every quotation you extended or moved, with its source file and page; every name or title you introduced, with where it comes from; and the word count. End with at most three sentences for the operator on what you changed and why.

## Markdown conventions

Keep the paper's format, because the paper is rendered from it:
- front matter with `title:` and `abstract:` and nothing else;
- section headings as `# Heading` with **no numbers**, since the template numbers sections itself;
- the reference list last, under `# References {-}`;
- notes as `[^n]` markers with `[^n]: text` definitions;
- block quotations with `>`, straight quotation marks (never curly), and `--` in page ranges.

The References list stays character for character.

## Where things are, and what to write

- **The paper:** `<run>/09_final/final.md`, unless the operator names another text.
- **Its file name:** run `python3 system/tools/polish.py name --run <run> --stage "structure polish"`. It prints the name to use, the paper's title followed by the stage in parentheses. If you cannot run commands, take the paper's line in `PAPERS/README.md` and add ` (structure polish)`.
- **What you may read:** anything in this folder. Do not search the web.
- **What you may write:** only the files below. Change nothing else in this folder.

Write:
1. **`<run>/12_polish/<name>.md`**: the complete restructured paper, with no commentary inside it. If your verdict is **leave**, do not write this file.
2. **`<run>/12_polish/<name> - notes.md`**: stages 1, 2, 3 and 5.

Then, if you can run commands:
3. **Count it:** `python3 system/tools/polish.py count "<run>/12_polish/<name>.md"`. The count must be at most 6,000.
4. **Render it:** `python3 system/tools/polish.py render "<run>/12_polish/<name>.md"`. This writes `<name>.tex` and `<name>.pdf` beside the paper and puts a copy of the PDF in `PAPERS/`. If it fails because pandoc or LaTeX is missing, do not install anything. Say so at the end, and Claude will render it.

If you cannot write files, reply in the chat instead: the complete paper first, then a line reading exactly `=== EDITOR'S NOTES ===`, then the notes. The operator will save them.
