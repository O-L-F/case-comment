# Case Comment PDF Template 

This guide was made for the few of us that do not think Word is the opportune 
software for writing. This template does not take stylistic aspects of any one
journal. It is simple. It looks nice.

It also has the added benefit of having a function inside that makes it much 
faster to include cases you want to cite. It uses the dataset published by Alschner,
Mathen & MacDonnell (2024) that you can find here :

`https://doi.org/10.5683/SP3/3YFSXV` 

The function automatically adds the case citation (McGill 10th) to your `bib` file.
Simply call our citation using [@case] and it will automatically be added to your 
references! To find the case, navigate the `.csv` file in the repo, find the case
name, and copy its ID. Then, run `scc("[ID]")`.

The pre-populated structure is meant to be malleable. You *should* change it to what
the journal, or your professor, is asking you. 

Jessica Giles, a lecturer at the Open University, has a [useful guide](https://law-school.open.ac.uk/sites/law-school.open.ac.uk/files/files/PILARS-Writing-case-comments.pdf)
for case comments. At p. 16 she goes over some ideas and common approaches to case comments. 

Another useful guide is [this ancient one](https://www.yorku.ca/khoosh/PPAS%202200/case_commentary.htm)
from York University's Osgoode Hall School of Law. It has a decent focus on the 
social and political implications of the case. 

## Files
- `case_comment_template.Rmd` — the R Markdown source. Edit the `params:`
  block for each new case comment (case name, citation, court, abstract,
  keywords, etc.), or pass params via `rmarkdown::render(..., params = list(...))`.
- `preamble.tex` — LaTeX include that produces the masthead, running
  header, Roman-numeral section headings, and footnote rule. Keep it in the
  same folder as the `.Rmd`.
- `citation.bib` — starter bibliography. Add entries with `@article{key, ...}`
  and cite them in the body as `[@key]` or `[@key at 138-40]`.

## Before you knit
1. **CSL file**: the YAML sets `csl: mcgill-en.csl`. The
   McGill Guide (10th ed.) CSL isn't in the default Zotero/CSL style
   [repository](https://www.zotero.org/styles), so place your own copy of 
   that `.csl` file in this same folder with that exact filename (or update the 
   `csl:` line to match whatever you named it).
2. **LaTeX engine**: requires `xelatex` (set via `latex_engine: xelatex`)
   plus a standard TeX Live install — `tinytex::install_tinytex()` in R is
   the easiest path if you don't already have LaTeX.
3. **Font**: `mainfont: "Times New Roman"` requires that font to be
   installed (common on Windows/Mac with MS Office; not always present on
   Linux). If it's missing, xelatex will error — swap it for
   `"Liberation Serif"` or `"TeX Gyre Termes"` instead.

