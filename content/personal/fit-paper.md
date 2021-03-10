+++
title = "Fit your paper into page limit"
+++

# Fit your paper into page limit

I collected the following techniques from my advisor Mohammad and
my labmate Prateesh.

```latex
% The following option preserves the space between words and letters,
% making it less likely to piss off your reviewers than the next option.
%\usepackage[subtle, lists=tight, wordspacing=normal, tracking=normal]{savetrees}

% The following option reduces the space between words and letters. Can save 0.5-1 column
% from a 12-page paper, but makes the paper slightly less readable.
\usepackage[subtle, lists=tight]{savetrees}

% Reduce the spacing around floats so that you do not need to manually set tons of \vspace.
\addtolength{\textfloatsep}{-0.2in} % spacing between floats and text
\addtolength{\floatsep}{-0.1in}     % spacing between two floats

% Make the section headings smaller.
\usepackage[small, compact]{titlesec}
\usepackage{titling}
\titlespacing*{\section}{0pt}{4pt}{3pt}
\titlespacing*{\subsection}{0pt}{3pt}{3pt}
\titlespacing*{\subsubsection}{0pt}{3pt}{3pt}
```
