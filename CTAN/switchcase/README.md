# switchcase

A powerful and user-friendly switch-case implementation for LaTeX, built on top of the `expl3` programming layer.

## Overview

The `switchcase` package provides structured control flow for LaTeX document authors and package developers. It supports:

- **String-based selection**: Compare a string against multiple values.
- **Integer-based selection**: Decision making based on integer expressions.
- **Environment-based syntax**: A clean, readable way to define cases without complex nesting of braces.
- **Global Scope**: Cases defined within an environment are globally collected, allowing for use inside loops and groups.
- **Safe Nesting**: Full support for nested `SwitchEnv` environments.

## Installation

1. Run `pdflatex switchcase.ins` to generate the `switchcase.sty` file.
2. Move `switchcase.sty` to your project directory or your local TeX tree.
3. (Optional) Run `pdflatex switchcase.dtx` to generate the technical documentation.

## Usage

### Command-based Switch

For simple, one-off switches, use the `\Switch` and `\IntSwitch` commands.

```latex
\usepackage{switchcase}

% String-based switch
\Switch{Apple}{
    {Apple} {This is an apple.}
    {Orange}{This is an orange.}
}[This is the default text.]

% Integer-based switch
\IntSwitch{2}{
    {1} {Result is one.}
    {2} {Result is two.}
}[Other number.]
```

### Environment-based Switch

The `SwitchEnv` environment provides a more modular approach, especially useful for complex logic.

```latex
\begin{SwitchEnv}{TargetValue}
    \Case{Option1}{Code for Option 1}
    \Case{TargetValue}{This code will execute!}
    \Default{Fallback code if no match is found.}
\end{SwitchEnv}
```

### Advanced: Nesting and Loops

`SwitchEnv` is designed to be robust. You can safely nest environments or use them inside `\foreach` loops and other groups.

```latex
\begin{SwitchEnv}{Outer}
    \Case{Outer}{
        \begin{SwitchEnv}{Inner}
            \Case{Inner}{Nested match!}
        \end{SwitchEnv}
    }
\end{SwitchEnv}
```

## License

Copyright (C) 2026 by Sergio Martinez-Losa
Distributed under the LaTeX Project Public License, version 1.3 or later.
