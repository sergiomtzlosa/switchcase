# switchcase

Switch-case implementation for LaTeX using expl3.

## Description

The `switchcase` package provides a user-friendly interface for switch-case
structures in LaTeX, built on top of the `expl3` programming layer. It supports
both string and integer-based case selection with an optional default case.

## Usage

```latex
\usepackage{switchcase}

% String switch
\Switch{Apple}{
    {Apple} {This is an apple.}
    {Orange}{This is an orange.}
}[Default action]

% Integer switch
\IntSwitch{2}{
    {1} {One}
    {2} {Two}
}[Other number]
```

## Installation

Run `pdflatex switchcase.ins` to generate the `.sty` file.
Run `pdflatex switchcase.dtx` to generate the documentation.

## License

Copyright (C) 2026 by Sergio Martinez-Losa
Distributed under the LaTeX Project Public License, version 1.3 or later.
