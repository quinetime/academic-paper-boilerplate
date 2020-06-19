# TEMPLATE FOR ACADEMIC PAPERS

This is a template that I clone in order to begin writing academic papers.  It's really for my own personal use, but others are free to make use of it.

## WORKFLOW

- Clone this directory
- Rename project in package.json
- Check that relative pathing for bibtex file is correct in package.json scripts
- Edit metadata in header.md
- *Optional:* run `git init` and `git add *`
- Write paper in four content files (content, footnotes, header, nocite)
- `npm run pdf` or `npm run latex` or `npm run word`
- *Optional:* generate aux file by converting the tex file into a pdf.  In JabRef, under the Tools menu, use the aux file to generate a sublibrary consisting of only the entries cited in the paper.
- *Optional:* edit LaTeX directly


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

[Curated LaTeX fonts, with descriptions](https://r2src.github.io/top10fonts/)

Personal favorites: venturis2, bookman

To include LaTeX packages, see [this post](https://tex.stackexchange.com/questions/139139/adding-headers-and-footers-using-pandoc/139205#139205).  This allows the use of any font installed on one's computer; see [here](https://tex.stackexchange.com/questions/3101/how-can-i-get-latex-to-use-the-fonts-that-are-already-on-my-pc-via-xetex/3104#3104).

## CITATIONS

[https://github.com/jgm/pandoc-citeproc/blob/master/man/pandoc-citeproc.1.md](https://github.com/jgm/pandoc-citeproc/blob/master/man/pandoc-citeproc.1.md)

[https://pandoc.org/demo/example19/Extension-citations.html](https://pandoc.org/demo/example19/Extension-citations.html)

example parameter: 

`--bibliography TestUnrealBib.bib`

Or, you can put the bibliography file data in the YAML header and remove the '--bibliography' parameter from the command



## NOCITE

In the nocite file, add the following (replacing the citations as needed). This will include papers in the bibliography even if they are not cited in the text.  (One writing strategy is to start by populating this list early with probable citations, then move them into the content as needed.)

Make sure to add an empty line before the following code.


```
---
nocite: |
	@BillonJD; @RadovicFU
...
```

## WORD COUNT

- [SublimeText package](https://github.com/kevinstadler/SublimeLaTeXWordCount)
- Use WinEDT (Document > Word Count)
- [texcount](https://app.uio.no/ifi/texcount/index.html)

## SPELLCHECK REMINDER

**F6** enables spellcheck in Sublime Text.


## TO INVESTIGATE

- It might be nice to create a default template that gets the latex to look as I want.
- Hanging indents in the bibliography section are very annoying to generate.  All the solutions I've seen require you to generate a References title in order to inject some LaTeX code afterward, instead of using the reference-section-title value in the YAML header.  See [here](https://dyrobooks.com/blog/2018/07/29/pandoc-and-hanging-indents/) and [here](https://tex.stackexchange.com/questions/477219/hanging-indents-with-a-pandoc-bibliography).


## USEFUL LINKS

[Boilerplating Pandoc for Academic Writing](https://www.soimort.org/notes/161117/)

[Sustainable Authorship in Plain Text using Pandoc and Markdown](https://programminghistorian.org/en/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown)

[Markdown and Pandoc for academic writing](http://arthurcgusmao.com/academia/2018/01/27/markdown-pandoc.html)

[Plain Text, Papers, Pandoc](https://kieranhealy.org/blog/archives/2014/01/23/plain-text/)
