---
layout: post
title: "Setting up github pages for Erlang module docs"
author: "Fred Youhanaie"
description: "Setting up github pages for Erlang module docs"
date: 2022-10-25
categories: general
---

While I was working on this web site with github pages and jekyll, I thought I
should revisit another "problem" I had been meaning to address. Which is the
online availability of the erlang module documentation for my own projects.

## About the Erlang documentation system

The [Erlang](https://erlang.org) library has a set of modules,
[edoc](https://www.erlang.org/doc/apps/edoc/chapter.html), for extracting the
documentation from the module source files and converting them to a set of html
files. It was inspired by Javadoc.

For applications that use `rebar3` the documentation can be generated easily
using the `rebar3 edoc` command, which produces the entire set of html pages and
stores them in the `doc/` directory. This is pretty common in most erlang
projects. All that one needs to do is to point the web browser to the index
page, `doc/index.html`. While this is simple for those working on the project,
it is very tedious for anyone who may want to inspect the documentation without
having to download the source code.

Some projects use <https://hex.pm/> for packaging and publishing their
applications. Hex, in addition to hosting the source code, also caters for
publishing the documentation, and provides links for browsing the documentation.
These can be found at <https://hexdocs.pm/>.

This is fine for the versions of the packages that have been published on hex,
but not for the latest versions under development, say, on github.

What I wanted to have was the automatic generation of the docs for the latest
version of the application, so that anyone curious about the project can inspect
the latest docs online.

And this is where github pages comes in.

With a bit of configuration, which involved some initial trial and error
activity, I was able to have the module docs auto-generated with every push to
the github repo.

## The per-repo github pages

Each project repository hosted on github can have its own set of web pages --
`github pages`.

This can be configured using the settings pages. The instructions can be found
here:
[Creating your site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-your-site).

The above link, as well as <https://pages.github.com/>, should be sufficient for
anyone wishing to have manually maintained web pages. However, for the module
docs we need to (re)generate the online pages automatically as and when the
source code is modified. For this I needed some additional configuration.

## The additional workflow tasks

My additional configuration can be summed up as follows:

1. Logged in to github and followed the link to the repository.
1. From the **Settings** page followed the **Pages** link on the left of the page.
1. Under **Build and deployment** and **Source** selected **Github Actions**.
1. Selected the **Configure** button, this showed an editor with a basic
   workflow file loaded. This acted as a template, which saved me from having to
   create one from scratch.
1. The above YAML file, `.github/workflow/pages.yml`, was saved and then used as
   the starting point for my own configuration.

The main changes from the default file supplied by github are as follows:

* The source directory for the main github pages is `./gh_pages`. This is used
  as container for any front matter for the module docs. Currently it contains
  the file `index.md`, which in turn contains links to the module docs.
  
* The jekyl pages are generated in a container that is run as user `root`, while
  everything else is executed as user `runner`. I added a task to change the
  owner of the jekyll generated files in the `_site` directory to user `runner`,
  so that we can drop our own files in the `_site` directory:

```
- name: take ownership of the site files
  run: sudo chown -R runner _site
```

* Two tasks contain the commands to generate the module docs and copy them to
  the `_site` directory. I generate two sets of docs, one for the exported
  (public) functions:

```
- name: generate the public edoc
  run: rebar3 edoc
- name: copy the doc files
  run: cp -r ./doc ./_site/edoc
```

and, the other covering ALL the functions, public and private:

```
- name: generate the full edoc
  run: rebar3 as dev edoc
- name: copy the doc files
  run: cp -r ./doc ./_site/edoc_dev
```

Once the modified workflow file was pushed to github the web pages were
generated automatically. And, from there on each `git push` kicked off a new
edoc run.

For an example see the [`espace
project`](https://github.com/fredyouhanaie/espace). The main files of interest
are
[`gh_pages/index.md`](https://github.com/fredyouhanaie/espace/blob/master/gh_pages/index.md)
and
[`.github/workflows/pages.yml`](https://github.com/fredyouhanaie/espace/blob/master/.github/workflows/pages.yml).
The auto-generated web pages can be seen
[here](https://fredyouhanaie.github.io/espace).

One last addition to the workflow file was to stop `yamllint` complaining about
the `on:` keyword not being a `truthy` value. This was fixed by replacing the
`on:` line with

```
on: # yamllint disable-line rule:truthy
```

---
