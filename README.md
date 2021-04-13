# `sphinxcontrib.svgbob` [![Stars](https://img.shields.io/github/stars/althonos/sphinxcontrib.svgbob.svg?style=social&maxAge=3600&label=Star)](https://github.com/althonos/sphinxcontrib.svgbob/stargazers)

*A Sphinx extension to render ASCII diagrams into SVG using [Svgbob](https://github.com/ivanceras/svgbob).*

[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square&maxAge=2678400)](https://choosealicense.com/licenses/mit/)
[![Source](https://img.shields.io/badge/source-GitHub-303030.svg?maxAge=2678400&style=flat-square)](https://github.com/althonos/sphinxcontrib.svgbob/)
[![GitHub issues](https://img.shields.io/github/issues/althonos/sphinxcontrib.svgbob.svg?style=flat-square&maxAge=600)](https://github.com/althonos/sphinxcontrib.svgbob/issues)

## 🗺️ Overview

To include diagrams into Sphinx documentation, diagrams are commonly described
with a dedicated markup language, and converted into an image by Sphinx when
the documentation is built. However, this reduces the legibility of the
documentation source for readers that are not browsing the HTML version.

[Svgbob](https://github.com/ivanceras/svgbob) is a diagramming model implemented
in Rust that can convert ASCII diagrams into SVG. Using it allows you to:

* Keep a textual version of the diagram in your documentation, so that it remains legible.
* Render a nicer version as SVG for HTML or PDF versions of the documentation.

## 💡 Example

Use the `svgbob` directive in a function docstring to show a diagram of what
is being computed:

```python
def hamming(x, y):
    """Compute the Hamming distance between two strings.

    Hamming distance between two strings of equal length is the number of
    positions at which the corresponding symbols are different. For instance,
    Hamming distance for a 3-bit string can be computed visually using a
    3-bit binary cube:

    .. svgbob::
       :align: center

                         110              111                          
                            *-----------*      
                           /|          /|
                          / |     011 / |     
                     010 *--+--------*  |
                         |  | 100    |  |
                         |  *--------+--* 101
                         | /         | /
                         |/          |/
                     000 *-----------*  001


    The minimum distance between any two vertices is the Hamming distance
    between the two bit vectors (e.g. 100→011 has distance 3).

    """
```

When Sphinx (and `autodoc`) renders the docstring of this function, you'll get
the following HTML page (here shown with the [Sphinx theme for readthedocs.org](https://github.com/readthedocs/sphinx_rtd_theme)):

![example1.html.png](https://raw.githubusercontent.com/althonos/sphinxcontrib.svgbob/master/static/example1.html.png)

And yet, the `help(hamming)` will still look nice and helpful:

![example1.console.png](https://raw.githubusercontent.com/althonos/sphinxcontrib.svgbob/master/static/example1.console.png)


## 💭 Feedback

### ⚠️ Issue Tracker

Found a bug ? Have an enhancement request ? Head over to the [GitHub issue
tracker](https://github.com/althonos/sphinxcontrib.svgbob/issues) if you need to report
or ask something. If you are filing in on a bug, please include as much
information as you can about the issue, and try to recreate the same bug
in a simple, easily reproducible situation.

### 🏗️ Contributing

Contributions are more than welcome! See [`CONTRIBUTING.md`](https://github.com/althonos/sphinxcontrib.svgbob/blob/master/CONTRIBUTING.md) for more details.


## 📚 Alternatives

* [`sphinxcontrib-kroki`](https://github.com/sphinx-contrib/kroki/) also lets you
  use Svgbob to convert ASCII diagrams, but it queries the
  [kroki.io](https://kroki.io/) website to do so, and does not support the
  new options from Svgbob v0.5.
* [`sphinxcontrib-aafig`](https://github.com/sphinx-contrib/aafig) uses the
  [`aafigure`](https://launchpad.net/aafigure) binary to convert ASCII diagrams.


## 🔨 Credits

`sphinxcontrib.svgbob` is developped and maintainted by:
- [Martin Larralde](https://github.com/althonos)

The structure of this repository was adapted from the aforementioned
`sphinxcontrib-kroki` repository, as I had no experience setting up a
Sphinx extension otherwise.


## ⚖️ License

This library is provided under the [MIT License](https://choosealicense.com/licenses/mit/).
