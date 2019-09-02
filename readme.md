### Why was this handbook created?

The aim of this handbook is to provide SADiLaR staff with day-to-day procedures and imporant SADiLaR policy documentation 


### Building this site

This site is built using the [Sphinx](http://www.sphinx-doc.org/en/stable/) documentation generator (a Python tool) and the [Read the Docs theme](https://github.com/rtfd/sphinx_rtd_theme) for the style. (Not to be confused with readthedocs.io - the site is _not_ hosted at readthedocs.io!) 

For more information about using Sphinx, see the [Getting Started guide (sphinx-doc.org)](http://www.sphinx-doc.org/en/stable/usage/quickstart.html) or the [Quick Start (readthedocs.io)](https://docs.readthedocs.io/en/latest/intro/getting-started-with-sphinx.html#quick-start) for an explanation of how to use Sphinx.

The [Carpentries Handbook](https://docs.carpentries.org/) was used as a base to build the SADiLaR Handbook Site.

#### Required dependencies

To install the required dependencies (Sphinx and the ReadTheDocs Sphinx theme), execute the following command from the repository directory to install all Python dependencies:

```
pip install -r requirements.txt 
```

After installing the dependencies, you can build the site locally by executing the following command from the repository:

```
$ make html
```

Open the file `_build/html/index.html` to preview the site locally. Python offers a quick way to run a web server to serve local files. Run the following:

```
$ cd _build/html

# Python 2:
$ python2 -m SimpleHTTPServer

# Python 3:
$ python3 -m http.server
```

In both cases, a local web server will be run on port `8000`, so navigate to <http://localhost:8000> in your browser to view the site locally.

You can make changes to the contents of the repository, and re-run `make html`, to update the website contents. If you are having problems with the site not refreshing, you can delete the contents of the `_build` directory (which are automatically generated) with `rm -fr _build/*`.

If new files or folders are added to the Handbook, `index.rst` will need to be updated for those to be included in the final site by Sphinx.

#### Site structure

The root level `index.rst` generates the main categories and the sidebar navigation.  Each sub-section is a folder in the `topic_folders` directory. Each folder within the `topic_folders` directory has its own `index.rst` file. These then expand into the subcategories in each directory.

Within each folder's `index.rst` file, the section heading is defined by a string of  `=` beneath it. Subheadings can be defined using `###` in each markdown file or by a heading with `-` under it in the `index.rst` file.

##### Formatting Hyperlinks

In markdown documents, links can be formatted in standard markdown, with the text in square brackets and the hyperlink in parentheses: 

```
[text](hyperlink)
```

For the `index.rst` files, links must be formatted as follows. Note the text is followed by the hyperlink in pointy brackets, everything is wrapped in backticks, and then followed by an underscore.

```
`text<hyperlink>`_

```

**Links to external markdown documents**

Something in this template causes `.md` extensions to get stripped, breaking links to things like markdown documents in a GitHub repo.  This can be fixed by adding an anchor tag (`#`) to the end of the url.  For example, `https://github.com/carpentries/handbook/blob/topic_folders/file.md` would become `https://github.com/carpentries/handbook/blob/topic_folders/file.md#`. 


#### Additional information

This site is built from the master branch of [this repo](https://github.com/zjsteyn/SADiLaR-Handbook).
