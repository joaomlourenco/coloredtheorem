# tcbtheorem

A colourful boxed theorem environment, combining `tcolorbox` and breakable boxes.  It supports full `tcolorbox` customization, automatic numbering, `\label{...}` and `\ref{…}`, and `\listof…`

## Introduction

The `tcbtheorem` package is a simple environment, which takes no options, and that allows to write stuff inside boxes from `tcolorbox`. So, this packages includes `tcolorbox`.
Akin to `\newtheorem` from the `amsmath` package, the user should start by defining a new theorem/box group and customize its aspect. Each new environment will have its own counter/numnering. Notice that `\label{...}` and `\ref{...}` work as expected. The is also a command to generate the corresponding list of …

## Commands

* `\tcbnewtheorem{<envname>}{<Name>}[<tcolorbox options>]`\
`      <envname>` is the environment name, e.g., theorem.\
`      <Name>` is the name for new environment being defined, e.g., Theorem.\
`      <tcolorbox options>` options to be passed to the `tcolorbox` environment to customize the boxes for the given environment (this argument is optional).\
* `\begin{<envname>}{<Caption>}[<tcolorbox options>]<Contents>\end{<envname>}`\
`      <envname>` is the environment name, e.g., theorem.\
`      <Caption>` is the caption/title of the box.\
`      <tcolorbox options>` options to be passed to the `tcolorbox` environment,
which will override the defaults given in `\tcbnewtheorem`.\
`      <Contents>` the contents to by typeset inside the coulored environment.
* `\listof<envname>s` wherer `<envname>` is the environment name, e.g., `\listoftheorems`. Please notice that there is a ‘s’ (plural) after `<envname>`, .

## Example

_As any dedicated reader can clearly see, the Ideal of practical reason is a representation of, as far as I know, the things in themselves; as I have shown elsewhere, the phenomena should only be used as a canon for our understanding. The paralogisms of practical reason are what first give rise to the architectonic of practical reason. As will easily be shown in the next section, reason would thereby be made to contradict, in view of these considerations, the Ideal of practical reason, yet the manifold depends on the phenomena. Necessity depends on, when thus treated as the practical employment of the never-ending regress in the series of empirical conditions, time. Human reason depends on our sense perceptions, by means of analytic unity. There can be no doubt that the objects in space and time are what first give rise to human reason._

Now, lets write again Algorithm 1, but now with a different visual!

_Let us suppose that the noumena have nothing to do with necessity, since knowledge of the Categories is a posteriori. Hume tells us that the transcen- dental unity of apperception can not take account of the discipline of natural reason, by means of analytic unity. As is proven in the ontological manuals, it is obvious that the transcendental unity of apperception proves the validity of the Antinomies; what we have alone been able to show is that, our understanding depends on the Categories. It remains a mystery why the Ideal stands in need of reason. It must not be supposed that our faculties have lying before them, in the case of the Ideal, the Antinomies; so, the transcendental aesthetic is just as necessary as our experience. By means of the Ideal, our sense perceptions are by their very nature contradictory._

Finally, let’s add another example here, this time using the default visual that was given when creating the environment with `\tcbnewtheorem`…

And now and example with no caption and a different visual... this example
will not go into the` \listofexamples` below!

Now we get the lists of algorithms (`\tcblistofalgorithms`) and examples (`\tcblistofexamples`). Remember to add the prefix `tcb`!

## List of Algorithms

## List of Examples


