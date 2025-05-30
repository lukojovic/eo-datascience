# Earth Observation Datascience


[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tuw-geo/eo-datascience/main)

This is a book on Earth Observation Datascience, consisting of common
workflows in Python at the Department of Geodesy and Geoinformation at
the TU Wien (Vienna Austria).

The workflows comprise exercises that utilize remote sensing
information, such as microwave backscattering from Sentinel-1 and
visible range imagery from Sentinel-2.

## Quarto

This book is based on [Quarto](https://quarto.org/), a literate
programming system for open-source scientific and technical documents.

## Contribute

You can contribute to this book by making a Pull Request. Make sure to
include your workflow as an `qmd` file to the chapters directory while
also creating an `environment.yml` file with the same name as quarto
document. This should ensure that the python code can be executed as a
standalone project. The `environment.yml`should be added to the
`notebooks` directory. It is not necessary to include the `ipynb` file,
as these will be generated automatically with GitHub actions. To include
the chapter to the book include your filename to the `_quarto.yml`. If
you have references, these should be included in the bibtex file
(`chapters/references.bib`).

To exemplify, adding `my_awesome_workflow.qmd` to the book requires the
following steps:

1)  Add `my_awesome_workflow.qmd` to the `chapters` directory
2)  Add `my_awesome_workflow.yml`to the `notebooks` directory
3)  Add `chapters/my_awesome_workflow.qmd` to the `chapters` list in the
    `_quarto.yml` file
4)  Add references to `chapter/references.bib`

Don’t worry if your original file is an Jupyter Notebook. Jupyter
notebooks can be easily converted to quarto files by using:

``` {bash}
quarto convert basics-jupyter.ipynb # converts to qmd
```

## Developing

The pre-commit hooks can be used to check whether outputs are empty.
This can be achieved, like so:

``` {bash}
pip install pre-commit
pre-commit install
```

The `git workflow` essentialy converts the quarto files in `chapters`
into jupyter notebooks, generates a file for the table of contents and
pushes these files together with the **Makefile** and the
**references.bib** files to the cookbook repository.
