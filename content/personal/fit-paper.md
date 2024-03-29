+++
title = "Fit your paper into 12 pages"
+++

# Fit your paper into 12 pages

I collected these techniques from my advisor Mohammad, my lab mate Prateesh,
and stackoverflow.

```latex
% The savetrees package provides a bunch of presets for saving space. I'm
% providing three sample configurations. The following option only shrinks
% lists (enums).
\usepackage[all=normal, lists=tight]{savetrees}
% The following option is more aggressive but still preserves the spacing
% between words and letters, making it less likely to piss off your reviewers
% than the next option would.
%\usepackage[subtle, lists=tight, wordspacing=normal, tracking=normal]{savetrees}
% The following option reduces the spacing between words and letters. It can
% save 0.5-1 column in a 12-page paper, but makes the paper slightly less
% readable.
%\usepackage[subtle, lists=tight]{savetrees}

% Reduce the spacing around all floats (figures) so that you do not need to
% manually set tons of \vspace. Adjust the values to your like.
\addtolength{\textfloatsep}{-0.2in} % spacing between floats and text
\addtolength{\floatsep}{-0.1in}     % spacing between two floats
\captionsetup[table]{font=small,skip=4pt} % spacing between caption and figure
\captionsetup[figure]{font=small,skip=4pt}

% Make the section headings smaller. It may not work with some templates, such
% as acmart.
\usepackage[small, compact]{titlesec}
\usepackage{titling}
\titlespacing*{\section}{0pt}{4pt}{3pt}
\titlespacing*{\subsection}{0pt}{3pt}{3pt}
\titlespacing*{\subsubsection}{0pt}{3pt}{3pt}

% Do not penalize widow and orphan lines
\widowpenalty=0 % Allow the end of a paragraph to overflow to the next page
\clubpenalty=0  % Allow the beginning of a paragraph to begin from the prev page
```
