# coloredtheorem

A colorful boxed theorem environment, combining `tcolorbox` and breakable boxes.  It supports full `tcolorbox` customization, automatic numbering, `\label{...}` and `\ref{…}`, and `\listof…`

<!--
--------

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="
      https://api.star-history.com/svg?repos=joaomlourenco/coloredtheorem&type=Date&theme=dark
    "
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="
      https://api.star-history.com/svg?repos=joaomlourenco/coloredtheorem&type=Date
    "
  />
  <img
    width="500"
    alt="Star History Chart"
    src="https://api.star-history.com/svg?repos=joaomlourenco/coloredtheorem&type=Date"
  />
</picture>

--------
-->

## About

* **Package:** coloredtheorem — A colorful boxed theorem environment
* **Copyright:** 2024 © João M. Lourenço <joao.lourenco@fct.unl.pt>
* **CTAN:** https://ctan.org/pkg/coloredtheorem
* **Repository:** https://github.com/joaomlourenco/coloredtheorem
* **License:** The LaTeX Project Public License 1.3c

## Introduction

The `coloredtheorem` package is a simple environment that allows to write stuff inside
boxes from `tcolorbox`. If necessary the boxes gracefully overflow to the next page.
This package takes no options and includes `tcolorbox` if necessary. You may include
`tcolorbox` with your own favourite options prior to including this package.

Akin to `\newtheorem` from the `amsmath` package, the user should start by defining a 
new _theorem/box_ group and customize its aspect. Each new environment will have its 
own counter/numnering. Notice that `\label{...}` and `\ref{...}` work as expected. 
There is also a command to generate the corresponding _\listof..._

## Usage

* `\usepackage{coloredtheorem}`
  * Load Load the `coloredtheorem` package. This package will load `tcolorbox` if necessary.
* `\cthnewtheorem{<envname>}{<Name>}[<tcolorbox options>]`
  * Create a new boxed algorithm-like environment.
    * `<envname>` is the suffix for the new environment being defined, e.g., `algoritm`. The effective environment name will be `cth<envname>`, e.g., `cthalgorithm`.
    * `<Name>` is the (printable) name or the new environment being defined, e.g., _Algorithm_.
    * `<tcolorbox options>` default options for the environment being defined (this argument is optional). These options are passed straight to the `tcolorbox` environment, so anything valid for `tcolorbox` is also valid here.
* `\begin{<envname>}{<Caption>}[<tcolorbox options>]<Contents>\end{<envname>}`
  * Create a new _algorithm-like_ box with the given contents.
    ∗ `<AltCaption>` is the alternative caption for the `\cthlistof<envname>s` (see below).
    * `<envname>` is the sffix for environment name, e.g., `algorithm`.
    * `<Caption>` is the caption/title of the box. If the caption is left empty, this box will not be listed with the `\cthlistof<envname>s` (see below).
    * `<tcolorbox options>` options to be passed to the `tcolorbox` environment, which will override the defaults given in `\cthnewalgorithm` (this argument is optional).
    * `<Contents>` the contents to by typeset inside the colored environment.
* `\listof<envname>s`
  * `<envname>` is the environment name suffix, e.g., `\cthlistofalgorithms`. Please
notice that there is a ‘s’ (plural) after `<envname>`.

## Example

Let’s start by creating two new environments, one for _algorithms_ and another for _examples_, both defaulting to a gray frame, the former with a yellowish background and the latter with a lighter gray background.

```latex
\cthnewtheorem{algorithm}{Algorithm}[coltitle=black, colback=yellow!10,
                                     colframe=black!15]
\cthnewtheorem{example}{Example}[coltitle=black, colback=black!5,
                                 colframe=black!30]
```

The box with Algorithm 1, which uses the default visual that was given when creating the environment with `\cthnewtheorem` and gracefully overflows onto the next page, was created with:

```latex
\begin{cthalgorithm}{Advance a counter to the next value in a domain
                    $\omega \in \mathbb{N}$.}

    Algorithm body here!
\end{cthalgorithm}
```

<img width="650" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/fa9cacce-89cc-4973-ac16-41a6e21dfded">

_(page break here)_

<img width="650" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/bc976d1a-2d7d-4f62-b651-4b23124d8d76">


The box Example 1, which uses the default visual for the environment (as given to `\cthnewtheorem...`), was created with:

```latex
\begin{cthexample}{This is an example!}
  Example body here!
\end{cthexample}
```

<img width="650" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/69bd5bbd-8da8-418f-805d-0837c62cfb2c">

Now, let’s create a new box for Algorithm 1, but with a different customized visual, which will affect only this entry! Notice that the customization argument is passed straight to the `tcolorbox` environment, so anything valid for `tcolorbox` is also valid here. Algorithm 2 was created with the following code:

```latex
\begin{cthalgorithm}
          {Advance a counter to the next value in a domain $\omega \in
                \mathbb{N}$, but now with a customized visual. Also, notice
                that this algorithm breaks the page boundaries.}
          [coltitle=white, colback=green!10, colframe=green!70!black,
                colbacktitle=\sffamily\bfseries\large, fonttitle=red!50!white]
  Algorithm body here!
\end{cthalgorithm}
```

<img width="650" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/977c371c-1ecb-43ca-9351-c4befc23f7e9">

_(page break here)_

<img width="650" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/c51ac463-c335-4132-9445-cb726ee616a1">

And now and example with no caption and a different visual... this example will not go into the` \listofexamples` below!

<img width="766" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/ab888abf-56ba-459d-aa94-2db9816d0a09">

Now let’s print the lists of algorithms and examples. Remember to add the prefix `cthth` to the `listof`, i.e., `\cthlistofalgorithms` and `\cthlistofexamples`!

## List of Algorithms
<img width="766" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/d2c4077e-ec5f-4b3d-8b24-a5713a8f3c29">

## List of Examples
<img width="767" alt="image" src="https://github.com/joaomlourenco/coloredtheorem/assets/2064643/483b6caf-f4f8-4e1c-83ff-f54101dad5f5">


