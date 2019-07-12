# TEMPLATE FOR ACADEMIC PAPERS

This is a template that I clone in order to begin writing academic papers.  It's really for my own personal use, but others are free to make use of it.

## WORKFLOW

- Clone this directory
- Rename project in package.json
- Check that relative pathing for bibtex file is correct in package.json scripts
- Edit metadata in header.md
- Write paper in four content files (content, footnotes, header, nocite)
- `npm run pdf` or `npm run latex` or `npm run word`
- Optional: generate aux file by converting the tex file into a pdf.  In JabRef, under the Tools menu, use the aux file to generate a sublibrary consisting of only the entries cited in the paper.
- Optional: edit LaTeX directly


## COMMAND LINE

`pandoc header.md content.md footnotes.md nocite.md --filter pandoc-citeproc -o processed/paper.pdf --bibliography ../../../../Bib/DubBib.bib`


## FOOTNOTES

Footnotes go in the separate footnotes file.

How to make footnotes: [https://www.markdownguide.org/extended-syntax/#footnotes](https://www.markdownguide.org/extended-syntax/#footnotes)


## YAML FRONT MATTER

The file `header.md` contains metadata and front matter in YAML format.  The csl file contains information about how citations should be formatted.  A file for APA style is included; delete the csl index in the header to revert to the Chicago Style default.

Other csl files can be downloaded here: [https://www.zotero.org/styles](https://www.zotero.org/styles)

The first YAML chunk contains material the reader can see.  The second YAML chunk contains matter pertaining to the bibliography.  The third YAML chunk contains formatting for the conversion into LaTeX.

LaTeX fonts can be found here: [https://tug.dk/FontCatalogue/](https://tug.dk/FontCatalogue/)

Good fonts: venturis2, bookman



## CITATIONS

[https://github.com/jgm/pandoc-citeproc/blob/master/man/pandoc-citeproc.1.md](https://github.com/jgm/pandoc-citeproc/blob/master/man/pandoc-citeproc.1.md)

[https://pandoc.org/demo/example19/Extension-citations.html](https://pandoc.org/demo/example19/Extension-citations.html)

example parameter: 

`--bibliography TestUnrealBib.bib`

Or, you can put the bibliography file data in the YAML header and remove the '--bibliography' parameter from the command



## NOCITE

In the nocite file, add the following (replacing the citations as needed). This will include papers in the bibliography even if they are not cited in the text.  (One writing strategy is to start by populating this list early with probable citations, then move them into the content as needed.)


```
---
nocite: |
	@BillonJD; @RadovicFU
...
```

## SPELLCHECK REMINDER

**F6** enables spellcheck in Sublime Text.


## POTENTIAL EDITS TO MAKE IN LATEX FILE

- Add `\noindent` to the inside of the abstract block, just before abstract content starts.


## TO INVESTIGATE

It might be nice to create a default template that gets the latex to look as I want.


## USEFUL LINKS

[Boilerplating Pandoc for Academic Writing](https://www.soimort.org/notes/161117/)

[Sustainable Authorship in Plain Text using Pandoc and Markdown](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)

[Markdown and Pandoc for academic writing](http://arthurcgusmao.com/academia/2018/01/27/markdown-pandoc.html)