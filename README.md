# Create a webpage for your project

Let's use [Mkdocs](https://www.mkdocs.org/) as it is the easiest tool to use.

## Setup

```bash
pip install mkdocs
```

Create the documentation directory and project for Mkdocs:

```bash
# Make sure you are in the root directory of your repo.
mkdocs new documentation
```

Now check the generated default webpage:

```bash
cd documentation
mkdocs serve
```

Go to your browser and copy the following address: http://127.0.0.1:8000/

The tool consists of two main parts:

* Documents that represent pages and are written in Markdown (`documentation/docs` folder)
* A configuration file to setup the whole webpage (`documentation/mkdocs.yml` file)


## Themes

Let's customize the webpage configuration:

Check all the themes at: https://github.com/mkdocs/mkdocs/wiki/MkDocs-Themes

A nice one: Material (sponsored by Google): https://github.com/squidfunk/mkdocs-material. Install it:

```bash
pip install mkdocs-material
```

Add the theme to the configuration file `mkdocs.yml`:

```yml
theme:
  name: material
```

## Documentation

Add an index and a webpage main name to your file `mkdocs.yml`:

```yaml
site_name: My Docs # Webpage main name

nav:
  - Home: index.md # Home page. The main page where you can see the index
  - Setup: setup.md # Other pages that you want to add to the webpage
```

Any new page that you will add to the webpage (e.g. setup) must be created
as a new file into `docs`.

## Create webpage

This creates the html files required for your webpage:

```bash
mkdocs build
# Make sure you are in the root of the repository
echo "documentation/site/" >> $(git rev-parse --show-toplevel)/.gitignore
```

To check how the wepbage will look like from your browser:

```bash
mkdocs serve
```

And then go to your browser and copy the following address: http://127.0.0.1:8000/

## Deployment

Let's deploy the webpage to GitHub pages. Make sure your repo is hosted in a GitHub repository before deploying the webpage.

```bash
cd documentation
mkdocs gh-deploy
```

## Customization

Check the documentation to know how to configure your site (github link, google analytics,...): https://www.mkdocs.org/user-guide/configuration/.

More documentation to customize the template can be found here: https://www.mkdocs.org/user-guide/configuration/.

### Annex

For Windows instead of `pip` or `mkdocs`commands, use:

```bash
python -m pip
python -m mkdocs {command}
```
