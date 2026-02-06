
Use the following user defined macros while adding images to the beamer presentation. \myfigbig is to be preferred for most images. /home/yogesh/work/images is where I will place images to be used in the presentation.

\newcommand{\myfigsmall}[1]{\begin{figure}
  \centering
  \includegraphics[width=0.75\textwidth,height=0.5\textheight,
    keepaspectratio]{/home/yogesh/work/images/#1}
\end{figure}}

\newcommand{\myfig}[1]{\begin{figure}
  \centering
  \includegraphics[width=0.85\textwidth,height=0.65\textheight,
    keepaspectratio]{/home/yogesh/work/images/#1}
\end{figure}}

\newcommand{\myfigbig}[1]{\begin{figure}
  \centering
  \includegraphics[width=0.9\textwidth,height=0.8\textheight,
    keepaspectratio]{/home/yogesh/work/images/#1}
\end{figure}}

