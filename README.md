# AppFit SDK Docs

## Getting Setup

The Docukent builder uses [MKDocs](https://www.mkdocs.org). In order to get things running and working as expected, we need to do a few things

### Installation

To install MKDocs, we want to use homebrew. This is as simple as running

```sh
brew install mkdocs
```

This will install everything needed into the correct python paths.\

## Getting the Project Up and Running

### Create a virtual environment

The easiest way to get things up and running on a more contained system, is to use virtual enviroments. To do this, simply run this command.

```sh
python3 -m venv /path/to/docs/appfit-sdk-docs/venv
```

### Install the Theme

In order to get MKDocs to build and generate things, we need to install the theme we want to use. Currently we are using the matieral theme, so lets get that installed using our new virtual environment

```sh
venv/bin/pip install mkdocs-material
```

### Running MKDocs

Once you have the theme installed, everything shuold be good to go, and all that is left is to run mkdocs and start viewing the documentation.

```sh
venv/bin/mkdocs serve
```

### Deploying

To deploy the docs, we need to generate them, this is as simple as running

```sh
venv/bin/mkdocs build
```

This will generate all of the static files you can use to deploy to your hosting provider.