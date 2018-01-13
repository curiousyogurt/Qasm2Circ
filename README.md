Qasm2Circ
=========
This is a fork of Issac Chuang's [qasm2circ](https://www.media.mit.edu/quanta/qasm2circ/).
This revision January 13, 2018

Changes:
--------

* Updated meter.eps with vector image (original meter.epsf renamed to old-meter.epsf)
* Changes l. 122 of xyqcirc.tex to use new meter image: [scale=.5] -> [scale=.47]; epsf -> eps

Brief Howto:
------------

1. Circuit.qasm file in <target> directory
2. Copy meter.eps from <qasm2circ> directory to <target>
3. python <qasm2circ>/qasm2tex.py Circuit.qasm > Circuit.tex
4. Modify the following lines in Circuit.tex

\documentclass[crop=true,preview=true]{standalone}
\input{../qasm2circ/xyqcirc.tex}

The purpose of qasm2tex.py is to create a PDF of the circuit which can then be included in the text file.
Then include the PDF into your LaTeX.  My suggestion is as follows, using the Overpic package:

    \begin{figure}
        \begin{minipage}{\textwidth}
        \begin{center}
            \begin{overpic}[width=0.85\textwidth]{Circuit}
                \put(x,y){Latex Text}
            \end{overpic}
            \caption{Circuit}
            \label{fig:Circuit}
        \end{center}
      \end{minipage}
    \end{figure}
