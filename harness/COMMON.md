# Common rules for every call (v12; focused reading v12.5)

You are one call in a short pipeline that writes a philosophy paper for a good general journal. Your output file is all that survives you: make it complete in itself, and write it for a philosopher, in plain prose.

1. **Files.** Read only what your spawn message lists. If file access is `device_bash`, do all reading and writing through `device_bash`, with paths under the machine folder; read long files in pieces (`sed -n`, `grep -n`); write with a quoted heredoc. Never delete anything.
2. **Budget.** Keep to the tool-use budget in your spawn message. Open a source at the pages you need (`grep -n` for a phrase, then `sed -n` around it) rather than reading it whole, and do not open a file twice.
3. **Knowledge and evidence.** Think with everything you know of the literature. But every quotation and page reference you put in a file must come from a text you opened in `02_corpus/sources/` (give its key and page). Anything else is marked `[from memory, unverified]`. Never invent a quotation, a page or a reference.
4. **Front matter.** Every output file begins with a `---` block holding the fields your role file names, then `---`.
5. **Language.** Use the literature's own terms. Define a technical term once. Do not coin labels for your own moves or for the paper's apparatus.
6. **Hand-back.** One line, exactly as the spawn message says. Nothing else.
7. **Focused reading (v12.5).** Where your mode asks you to read before you judge, read the closest antecedents, the target's latest statement and any successor argument that bears on the claim, and the passages on which the central inference depends, with enough surrounding context to assess them. Do not read every held text or check the whole corpus. A decisive claim of novelty, priority or defeat rests on a passage you opened (key and page), never on a note, an abstract, a fetch-tool extract or the absence of a keyword. A text you could not open is a stated limit, never clearance.
