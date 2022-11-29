---
title: "How to Update This Website"
date: 2021-01-21T19:29:47-03:00
Description: ""
Summary: "A cookbook to install, build, and update this website."
Tags: [hugo]
Categories: [website]
DisableComments: false
---

# Installation

## On Fedora

```bash
sudo dnf install hugo
```

## Git

```bash
git clone https://github.com/danielfcollier/danielfcollier.github.io.git
```

## Update submodules

```bash
git submodule init
git submodule update
```

# Updating

## Update theme installation

```bash
git submodule update --remote --merge
```

## Adding a new post

```bash
hugo new post/my-new-post.md
```

## List drafts

```bash
hugo list drafts
```

# Build

```bash
hugo -D
```

## Start server

```bash
hugo server -D
```

# Deploy

On pushing to the `main` branch a GitHub action will take place to deploy to GitHub Pages.

# About Hugo

Written in Go, Hugo is an open source static site generator available under the [Apache Licence 2.0.](https://github.com/gohugoio/hugo/blob/master/LICENSE) Hugo supports TOML, YAML and JSON data file types, Markdown and HTML content files and uses shortcodes to add rich content. Other notable features are taxonomies, multilingual mode, image processing, custom output formats, HTML/CSS/JS minification and support for Sass SCSS workflows.

Hugo makes use of a variety of open source projects including:

- https://github.com/yuin/goldmark
- https://github.com/alecthomas/chroma
- https://github.com/muesli/smartcrop
- https://github.com/spf13/cobra
- https://github.com/spf13/viper

Hugo is ideal for blogs, corporate websites, creative portfolios, online magazines, single page applications or even a website with thousands of pages.

Hugo is for people who want to hand code their own website without worrying about setting up complicated runtimes, dependencies and databases.

Websites built with Hugo are extremelly fast, secure and can be deployed anywhere including, AWS, GitHub Pages, Heroku, Netlify and any other hosting provider.

Learn more and contribute on [GitHub](https://github.com/gohugoio).

# References

- https://gohugo.io/
- https://github.com/lxndrblz/anatole
