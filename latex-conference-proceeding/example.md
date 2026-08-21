These are generic fallbacks only. If the user supplies a conference
template, use its own figure/table conventions and document skeleton
instead of the ones below — the ones below exist solely for the case where
no template has been supplied.

## Figure macro

Article-class figures are single-column-width by default; use the starred
`figure*` environment only inside a two-column layout when a figure must
span both columns, and only if the template permits it.

```latex
\newcommand{\myfig}[2]{%
  \begin{figure}[t]
    \centering
    \includegraphics[width=\columnwidth]{/home/yogesh/work/images/#1}
    \caption{#2}
    \label{fig:#1}
  \end{figure}}
```

Usage: `\myfig{ncralogo.jpg}{Short, self-contained caption text.}`

## Table convention

Captions go above tables, below figures, unless the template says otherwise.

```latex
\begin{table}[t]
  \centering
  \caption{Short table caption.}
  \label{tab:example}
  \begin{tabular}{lcc}
    \hline
    Quantity & Value & Unit \\
    \hline
    $T_{\rm eff}$ & 5778 & K \\
    \hline
  \end{tabular}
\end{table}
```

## Generic fallback article skeleton

Use only when the user has supplied neither a template nor the name of a
target proceedings series. Mark clearly in a leading comment that this is a
placeholder class to be swapped for the venue's required class file.

```latex
% NOTE: no conference template was supplied. This uses a generic
% two-column article layout as a placeholder. Replace \documentclass and
% any venue-specific packages with the actual proceedings class before
% submission.
\documentclass[11pt,twocolumn]{article}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage{graphicx}
\usepackage{amsmath,amssymb}
\usepackage{natbib}
\usepackage{hyperref}

\title{Paper Title}
\author{First Author$^{1}$ \and Second Author$^{2}$}
\date{}

\begin{document}
\maketitle

\begin{abstract}
Abstract text.
\end{abstract}

\noindent\textbf{Keywords:} keyword one, keyword two

\section{Introduction}

\section{Data / Methods}

\section{Results}

\section{Discussion}

\section{Conclusions}

\section*{Acknowledgments}

\bibliographystyle{plainnat}
\bibliography{references}

\end{document}
```
