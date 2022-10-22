---
title: "How to Update This Website"
date: 2021-01-21T19:29:47-03:00
Description: ""
Summary: "A cookbook to install, build, and update this website."
Tags: [cli, hugo]
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

## Adding content
```bash
hugo new post/my-new-post.md
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

On pushing to the *main* branch a GitHub action will take place to deploy to GitHub Pages.

# References
- https://gohugo.io/
- https://github.com/lxndrblz/anatole