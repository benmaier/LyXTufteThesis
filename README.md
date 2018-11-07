# LyXTufteThesis

A LyX template for PhD theses at HU Berlin. This is tailored to be compliant with the rules of
the Mathematisch-Naturwissenschaftliche Fakultät.

## Some Notes

* In order to compile this document with `biblatex` instead ot `natbib`, I tweaked the LyX-layout to
not include `natbib.sty` by standard. If you're using the layout-file, please note that you have to
load the document class with the `nobib` option for it to work.
* The toc in tufte-book is usually rather slim with references to chapters only. Since this is not
compliant with the standard toc of dissertations, load the class with the `notoc` option
* I've added the following additional preamble
```latex
\setcounter{secnumdepth}{3}
\setcounter{tocdepth}{3}

\usepackage{titlesec}
\usepackage{graphicx}
\usepackage{afterpage}

\newenvironment{changemargin}[2]{%
\begin{list}{}{%
\setlength{\topsep}{0pt}%
\setlength{\leftmargin}{#1}%
\setlength{\rightmargin}{#2}%
\setlength{\listparindent}{\parindent}%
\setlength{\itemindent}{\parindent}%
\setlength{\parsep}{\parskip}%
}%
\item[]}{\end{list}}


\geometry{bindingoffset=0.9cm}

\usepackage{xpatch}
\AtBeginDocument{\xapptobibmacro{cite}{\setunit{\nametitledelim}\printfield{year}}{}{}}

```

## Some Links

Here's a collection of links I needed to put this together.

### HU Berlin templates

* https://edoc-info.hu-berlin.de/de/zentral/dokumentvorlagen

### Nomenclature

* http://texdoc.net/texmf-dist/doc/latex/nomencl/nomencl.pdf
* https://tex.stackexchange.com/questions/114560/lyx-and-list-of-acronyms

### Citations in footnotes

* `biblatex` in `tufte-book`: https://github.com/Tufte-LaTeX/tufte-latex/issues/60
* https://tex.stackexchange.com/questions/45934/can-i-use-biblatex-with-tufte-classes
* https://tex.stackexchange.com/questions/253132/biblatex-footcite-style/258431
* https://tex.stackexchange.com/questions/342485/biblatex-footcite-customizing-biblatex-and-bibliography-style
* https://tex.stackexchange.com/questions/165481/biblatex-last-name-only-in-footcite
* https://tex.stackexchange.com/questions/75837/customizing-biblatex-styles-using-usebibmacro
* https://tex.stackexchange.com/questions/390682/author-index-building-and-footfullcite-command/390702#390702
* https://tex.stackexchange.com/questions/39206/biblatex-per-entry-changes-to-citation-field
* https://tex.stackexchange.com/questions/131844/shortening-margin-citations-in-tufte-class (if you use `\AtEveryCiteKey`,
make sure you clear fields without linebreaks in between because it will change the appearance of the footnote-citation

### TOC in tufte-book
* https://tex.stackexchange.com/questions/121790/how-to-generate-a-full-width-table-of-contents-tufte-book

### Improve your bib-file
* https://github.com/nschloe/betterbib

### LyX layout files
* https://tex.stackexchange.com/questions/236332/installing-new-lyx-layout-where-are-my-layout-files
* http://blog.anidear.com/2011/03/lyx-convert-latex-cls-file-to-layout-in.html

### Figure placement problems
* https://tex.stackexchange.com/questions/37726/problem-with-captions-at-top-of-page-for-tufte-latex
* https://tex.stackexchange.com/questions/48140/what-shell-commands-are-executed-by-lyx-view-menus

### Protected references are necessary
* https://tex.stackexchange.com/questions/191043/error-using-ref-in-captions-with-tufte-and-babel

### Margin figures have to be adjusted manually
* https://groups.google.com/forum/#!topic/tufte-latex/s5ySzb9fF50
