---
title: Cross referencing between different files in Overleaf
date: 2025-10-14
---

If you want to cite the figures or tables in the supplementary, you can refer to this setup. 


Here is `main.tex`
```latex
%%%%
% (from an answer by cyberSingularity at http://tex.stackexchange.com/a/69832/226)
%%%

\documentclass[12pt]{article}

\usepackage{xcite}

\usepackage{xr}
\makeatletter
\newcommand*{\addFileDependency}[1]{
  \typeout{(#1)}
  \@addtofilelist{#1}
  \IfFileExists{#1}{}{\typeout{No file #1.}}
}
\makeatother

\newcommand*{\myexternaldocument}[1]{%
    \externaldocument{#1}%
    \addFileDependency{#1.tex}%
    \addFileDependency{#1.aux}%
}

\myexternaldocument{supp}

\begin{document}

Label1 is section \ref{label1} in supp.tex.
%Suppose you have a figure in `supp.tex`, you want to cite the figure using \ref{label_of_fig_in_supp}.

\end{document}

```
Here is `supp.tex`

```latex
\documentclass{article}


\begin{document}

\section{Label1}
\label{label1}

This is referenced by file1.

\end{document}
```

You must include a file named `latexmkrc`. No extension with this file. 
Here is `latexmkrc`

```latex
add_cus_dep( 'tex', 'aux', 0, 'makeexternaldocument' );

sub makeexternaldocument {
    # if the dependency isn't one of the files that this latexmk run will consider, process it
    # without this test, we would get an infinite loop!
    if (!($root_filename eq $_[0]))
    {   # PLEASE ENABLE ONLY ONE OF THE FOLLOWING
        # DEPENDING ON THE ENGINE YOU'RE USING
    
        # FOR PDFLATEX
        system( "latexmk -pdf \"$_[0]\"" );

        # FOR LATEX+DVIPDF
        # system( "latexmk \"$_[0]\"" );

        # FOR XELATEX
        # system( "latexmk -xelatex \"$_[0]\"" );
        
        # FOR LUALATEX
        # system( "latexmk -lualatex \"$_[0]\"" );
   }
}
```