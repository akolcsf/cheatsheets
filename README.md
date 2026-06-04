# Cheatsheets

Cheatsheets for exams and LaTeX templates for building compact, efficient reference sheets.

## Probability End-Term Cheatsheet

Compact LaTeX cheatsheet for the Probability part of **Probability & Stochastic Processes (1)**.
Most of the formulas and definitions are derived from Prof. Shen's lecture slides, with additional notes added during revision.

## Files

- `cheatsheet.tex`: main cheatsheet content.
- `probability-cheatsheet.sty`: reusable LaTeX template for dense multi-column math cheatsheets.
- `cheatsheet.pdf`: compiled preview.
- `LICENSE`: MIT license for the repository.

## Build

Install a LaTeX distribution with the packages used by the template, then run:

```powershell
pdflatex cheatsheet.tex
```

The template depends on common TeX Live packages including `geometry`, `multicol`, `amsmath`, `mathtools`, `derivative`, `upgreek`, `iwona`, `enumitem`, `tikz`, `soul`, `tcolorbox`, and `listings`.

## Template Usage

Use the style file in another cheatsheet by placing `probability-cheatsheet.sty` beside your `.tex` file:

```latex
\documentclass[landscape,a4paper]{article}
\usepackage{probability-cheatsheet}

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

The package provides the compact page layout, the `card` environment, list spacing, highlighting via `\emph`, and probability/math helper macros such as `\PP`, `\EE`, `\var`, `\cov`, `\C`, and `\e`.
