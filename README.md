# coloredtheorem

A LaTeX package with a colourful boxed theorem environment, combining `tcolorbox` and breakable boxes.  It supports full `tcolorbox` customization, automatic numbering, `\label{...}` and `\ref{…}`, and `\listof…`

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

## Introduction

The `coloredtheorem` package is a simple environment, which takes no options, and that allows to write stuff inside boxes from `tcolorbox`. So, this packages includes `tcolorbox` if necessary. You may include `tcolorbox` with your own favourite options prior to including this package.

Akin to `\newtheorem` from the `amsmath` package, the user should start by defining a new theorem/box group and customize its aspect. Each new environment will have its own counter/numnering. Notice that `\label{...}` and `\ref{...}` work as expected. The is also a command to generate the corresponding `\listof...`

## Usage

* `\cthnewtheorem{<envname>}{<Name>}[<tcolorbox options>]`
  * Load the tcbtheorem package. This package will load tcolorbox if not already loaded.
* `\cthnewtheorem{<envname>}{<Name>}[<tcolorbox options>]`
  * `<envname>` is the environment name, e.g., theorem.
  * `<Name>` is the name for new environment being defined, e.g., Theorem.
  * `<tcolorbox options>` options to be passed to the `tcolorbox` environment to customize the boxes for the given environment (this argument is optional).
* `\begin{<envname>}{<Caption>}[<tcolorbox options>]<Contents>\end{<envname>}`
  * `<envname>` is the environment name, e.g., theorem.
  * `<Caption>` is the caption/title of the box.
  * `<tcolorbox options>` options to be passed to the `tcolorbox` environment, which will override the defaults given in `\cthnewtheorem`.
  * `<Contents>` the contents to by typeset inside the coulored environment.
* `\listof<envname>s`
  * Where `<envname>` is the environment name, e.g., `\listoftheorems`. Please notice that there is a ‘s’ (plural) after `<envname>`.

## Example

Let’s start by creating two new environments, one for algorithms and another for examples, both defaulting to a gray frame, the former with a yellowish background and the latter with a lighter gray background.

    \cthnewtheorem{algorithm}{Algorithm}[coltitle=black, colback=yellow!10,
                                         colframe=black!15]
    \cthnewtheorem{example}{Example}[coltitle=black, colback=black!5,
                                     colframe=black!30]

An algorithm box will be created with:

    \begin{cthalgorithm}{Advance a counter to the next value in a domain
                        $\omega \in \mathbb{N}$.}

        Algorithm body here!
    \end{cthalgorithm}

<img width="491" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/54147631-3f5d-4ae0-a8b7-8b18b48d8db2">

Now, let's rewrite Algorithm 1, but now with a different customized visual, just for this entry! The customization (3rd) argument is passed straight to the `tcolorbox` environment, so anything valid for `tcolorbox` is also valid here.

<img width="491" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/be180e78-bc59-48ff-9efa-a26af5dae0bd">

(page break here!)

<img width="489" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/04c6fcaa-1a27-4550-8b17-2ae4d90809b0">

Now, let’s add an example here, this time using the default visual that was given when creating the environment with `\cthnewtheorem`…

<img width="490" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/835c1537-5b18-48b6-8ac1-ba6a6cff7b1b">

And now and example with no caption and a different visual... this example will not go into the` \listofexamples` below!

<img width="492" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/329e61a9-a12b-4cfe-9edf-1977f8158ee9">

Now let’s print the lists of algorithms and examples. Remember to add the prefix cthth to the listof, i.e., `\cthlistofalgorithms` and `\cthlistofexamples`!

## List of Algorithms
<img width="492" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/f935bfcb-3387-426e-8511-c1f0efdcdd85">

## List of Examples
<img width="487" alt="image" src="https://github.com/joaomlourenco/tcbtheorem/assets/2064643/033f83d4-24c3-4e9d-8947-135f5765e3f3">


