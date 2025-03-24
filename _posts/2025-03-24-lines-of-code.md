---
layout: post
title: How To Count Lines of Code in a GitHub Repository?
date: 2025-03-24
category: productivity
author: 
tags: [git]
summary: 
---

If you’ve ever wanted to quickly measure how much code you or your team have written in a Git repository, there’s a neat little command-line trick that can help — without the need for manually downloading ZIPs or scanning the entire project history. Enter: `cloc-git`.

The StackOverflow answer to “Can you get the number of lines of code from a GitHub repository?” shares a clever one-liner using cloc and Git:

```sh
git clone https://github.com/some/repo.git
cd repo
cloc .
```

Want to make this reusable? [Wrap it into a script](https://stackoverflow.com/questions/26881441/can-you-get-the-number-of-lines-of-code-from-a-github-repository/29012789#29012789):

```sh
#!/usr/bin/env bash
git clone --depth 1 "$1" temp-linecount-repo &&
  printf "('temp-linecount-repo' will be deleted automatically)\n\n\n" &&
  cloc temp-linecount-repo &&
  rm -rf temp-linecount-repo
```
