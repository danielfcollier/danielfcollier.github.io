---
title: "Contributing to Open Source Projects"
date: 2022-10-21T19:49:13-03:00
Description: ""
Summary: "Summary with git commands to get started and update to Open Source on GitHub"
Tags: [cli, git, oss]
Categories: [git]
DisableComments: false
---

# Projects with my contributions

- API Dev Tools: [_JSON Schema $Ref Parser_](https://github.com/APIDevTools/json-schema-ref-parser)

# GitHub Flow

## Fork the repository

On the GitHub repository, use the page UI to fork the repository.

## Clone the repository

```bash
git clone https://github.com/<my-username>/<forked-repository>.git
```

## Configure a Remote for the fork

```bash
git remote add upstream https://github.com/<original-owner-username>/<forked-repository>.git
```

Check the result with:

```bash
git remote -v
```

## Sync the fork

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

# Adding New Features for a PR

## Feature branch

```bash
git push --set-upstream origin <feature-branch>
```

## Make a PR

Once the `<feature-branch>` is completed, go to the original forked repository and create a "New Pull Request" - specify the forked repository and the feature branch. Add notes to enrich the PR to increase the acceptance, and go along with required changes by the maintainer(s) of the project.

# References:

- https://www.digitalocean.com/community/tutorials/how-to-create-a-pull-request-on-github
