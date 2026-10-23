# withdraw

A small LaTeX package for typesetting withdrawal schedules: four-column
tables that track a drawdown plan year by year, one row per year with the
withdrawal taken, the end balance, and the survival check that flags where
a plan breaks, plus small-print notes and assumptions lines.

## Usage

```latex
\documentclass{article}
\usepackage{withdraw}

\begin{document}

\begin{withdrawal}{Plan A, real terms}
  \wrsource{4\% initial rate, inflation-adjusted after}
  \withdrawrow{1}{40{,}000}{962{,}000}{pass}
  \withdrawrow{2}{41{,}600}{879{,}000}{pass}
  \withdrawrow{3}{43{,}264}{748{,}000}{pass}
  \withdrawrow{4}{44{,}995}{590{,}000}{pass}
  \withdrawrow{5}{46{,}795}{401{,}000}{tight}
\end{withdrawal}
\wrnote{Numbers are illustrative; a bad early sequence shows up in the
check column long before the balance hits zero.}

\end{document}
```

Commands:

- withdrawal{title} environment opens the table;
- wrsource{text}: an assumptions line under the title;
- withdrawrow{year}{withdrawal}{balance}{check}: one plan year;
- wrnote{text}: a small-print note under the table.

The package depends only on the standard array package. See
https://firenomics.com for worked withdrawal-rate and sequence-risk
write-ups.
