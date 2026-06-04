# Cheatsheets

Reusable LaTeX templates and exam cheatsheets. The repository is organized so more courses can be added without tying the templates to a single subject.

## Templates

- `eng-cheatsheet.sty`: compact English/math cheatsheet template.
- `zh-cheatsheet.sty`: compact Chinese/math cheatsheet template based on `ctex`.

Both templates provide:

- landscape A4 layout with tight margins;
- multi-column `cheatsheetcolumns` environment;
- dashed `card` boxes for topic blocks;
- compact list and code-listing settings;
- common math helper macros such as `\ii`, `\e`, `\oo`, `\cc`, `\Ftrans`, and `\Ltrans`.

`eng-cheatsheet.sty` also includes probability helpers such as `\PP`, `\EE`, `\var`, `\cov`, and `\C`.
`zh-cheatsheet.sty` adds Chinese font defaults, ctex support, Iwona math digit handling, and `\Rnum` for Roman numerals.

## Current Cheatsheets

- `Probability/`: Probability part of **Probability & Stochastic Processes (1)**.
- `Complex Functions/`: Chinese cheatsheet for Complex Functions.

Each course directory contains its own `cheatsheet.tex` and compiled `cheatsheet.pdf`.

## Build

Build from the corresponding course directory so the relative template path resolves cleanly.

English/template-based courses:

```powershell
cd Probability
pdflatex cheatsheet.tex
```

Chinese/ctex courses:

```powershell
cd "Complex Functions"
xelatex cheatsheet.tex
```

The Chinese template is intended for XeLaTeX or LuaLaTeX because it uses `ctex`.

## Starting a New Cheatsheet

For an English cheatsheet:

```latex
\documentclass[landscape,a4paper]{article}
\makeatletter
\def\input@path{{../}}
\makeatother
\usepackage{eng-cheatsheet}

\begin{document}
\begin{cheatsheetcolumns}
  \begin{card}{Topic}
    \begin{itemize}
      \item Key formula: $\EE[X]=\sum_x xp_X(x)$.
    \end{itemize}
  \end{card}
\end{cheatsheetcolumns}
\end{document}
```

For a Chinese cheatsheet:

```latex
\documentclass[landscape,a4paper]{ctexart}
\makeatletter
\def\input@path{{../}}
\makeatother
\usepackage{zh-cheatsheet}

\begin{document}
\begin{cheatsheetcolumns}
  \begin{card}{主题}
    \begin{itemize}
      \item 关键公式：$f^{(n)}(z)=\odv[n]{f}{z}$.
    \end{itemize}
  \end{card}
\end{cheatsheetcolumns}
\end{document}
```
