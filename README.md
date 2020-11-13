# TEMPLATE FOR ACADEMIC PAPERS

This is a template that I clone in order to begin writing academic papers.  It's really for my own personal use, but others are free to make use of it.

## WORKFLOW

- Clone this repository with `git clone https://github.com/quinetime/academic-paper-boilerplate PROJECT_NAME`
- In `package.json`:
    - Rename project (spaces not allowed)
    - Check that relative pathing for bibtex file is correct in scripts
- *Optional:* remove `.gitignore` files from `processed` or `notes` directories if you would like their contents version controlled
- Edit metadata in header.md
- Write paper in four content files (content, footnotes, header, nocite)
- `npm run pdf` or `npm run latex` or `npm run word` or `npm run pdf-font` (for a PDF with an arbitrary font)

## YAML FRONT MATTER

The file `header.md` contains metadata and front matter in YAML format.  

The first YAML chunk contains material the reader can see.  The second YAML chunk contains matter pertaining to the bibliography.  The third YAML chunk contains formatting for the conversion into LaTeX.

LaTeX fonts can be found [here](https://tug.dk/FontCatalogue/). See also [curated LaTeX fonts, with descriptions](https://r2src.github.io/top10fonts/).  Personal favorites: venturis2, bookman.  To use arbitrary fonts installed on one's machine, edit the `headerfont.md` file instead of `header.md`, and use the command `npm run pdf-font` on the command line. Doing so will have pandoc use xelatex instead of pdflatex, which results in the loss of some microtypography.

LaTeX packages can be added either to the header (using `header-includes:`) or to the `texheader.tex` file, but doing the former requires manually installing them first and you'll get an error if they aren't installed.  Adding them in `texheader.tex` should bring up a prompt if they aren't installed.

## FOOTNOTES

Footnotes go in the separate footnotes file.

[How to make footnotes](https://www.markdownguide.org/extended-syntax/#footnotes).


## CITATIONS

[Info about how to cite using pandoc-citeproc](https://github.com/jgm/pandoc-citeproc/blob/master/man/pandoc-citeproc.1.md).

[More info from the main pandoc site](https://pandoc.org/demo/example19/Extension-citations.html).

The scripts that run pandoc include a parameter with reference to a bibtex file: e.g. `--bibliography TestBib.bib`. You can alternately put the bibliography file data in the YAML header and remove the '--bibliography' parameter from the command scripts.

The csl file contains information about how citations should be formatted.  A file for APA style is included; delete the csl index in the header to revert to the Chicago Style default. Other csl files can be downloaded [here](https://www.zotero.org/styles).

### NOCITE

In the nocite file, add the following (replacing the citations as needed). This will include papers in the bibliography even if they are not cited in the text.  (One writing strategy is to start by populating this list early with probable citations, then move them into the content as needed.)

Make sure to add an empty line before the following code.

```
---
nocite: |
	@BillonJD; @RadovicSDNE
...
```
If no nocite references are added, you'll get a warning on creating your document, but it doesn't matter.

### WORKS CITED SECTION

The file `bib-header.tex` fixes the formatting of the Works Cited section in PDFs.  

Because of this, a reference-section-title value in the YAML header cannot be used.  Instead, *Works Cited* is given as a section header in the `bib-header.tex` file.  Be aware of this when generating Word documents or other types.

### CREATING A BIB FILE

Once the paper is complete, create a tex file, then convert the tex file into a pdf using WinEDT or some other LaTeX processor.  This will create an aux file (which pandoc normally does not expose). 

In JabRef, under the Tools menu, use the aux file to generate a sublibrary consisting of only the entries cited in the paper.

## FORMATTING TIPS

### LINE NUMBERING

Comment out or uncomment the appropriate section of `tex-header.md` to disable or enable line numbering.

### DOUBLESPACING

Add `linestretch: 2` to header.

### PAGE HEADINGS

Add `pagestyle: headings` to header.

### ENDNOTES INSTEAD OF FOOTNOTES

Uncomment the appropriate section of `tex-header.md` and add the chunk specified within to `bib-header.tex`.


## TEXT EDITING REMINDERS

### WORD COUNT

- [SublimeText package](https://github.com/kevinstadler/SublimeLaTeXWordCount)
- Use WinEDT (Document > Word Count)
- [texcount](https://app.uio.no/ifi/texcount/index.html)




### SPELLCHECK

**F6** enables spellcheck in Sublime Text.



## USEFUL LINKS

[Boilerplating Pandoc for Academic Writing](https://www.soimort.org/notes/161117/)

[Sustainable Authorship in Plain Text using Pandoc and Markdown](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)

[Markdown and Pandoc for academic writing](http://arthurcgusmao.com/academia/2018/01/27/markdown-pandoc.html)

[Plain Text, Papers, Pandoc](https://kieranhealy.org/blog/archives/2014/01/23/plain-text/)

[Simple Essay](https://github.com/plain-plain-text/simple-essay)
