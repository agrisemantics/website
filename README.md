# Agrisemantics

Backend for https://agrisemantics.github.io.

#### Build the website using MkDocs

* Install [mkdocs](http://mkdocs.org) on your machine (see [installation instructions](http://www.mkdocs.org/#installation)).
* Run the command `mkdocs gh-deploy` (or use [deploy.sh](https://github.com/agrisemantics/agrisemantics.github.io)).  
    * This command creates (or refreshes) the website at [https://agrisemantics.github.io/](https://agrisemantics.github.io/).  
    * The command must be run from the root directory of this repo.  
    * Behind the scenes, `mkdocs gh-deploy` builds HTML docs from the Markdown sources, uses the `ghp-import` tool to commit them to the `gh-pages` branch, and pushes the `gh-pages` branch to GitHub.

#### Using [Git Large File Storage](https://git-lfs.github.com/)

* Install in every local copy of the repo with with `git lfs install`
* See [`.gitattributes`](https://github.com/agrisemantics/website/blob/master/.gitattributes) for list of file types stored using Github LFS.
  * Initially, ZIP files are stored with LFS.
