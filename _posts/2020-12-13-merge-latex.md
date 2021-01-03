---
layout: post
title: Merging Multiple Latex Files
date: 2020-12-13 11:36
category: productivity 
tags: [latex, merge]
---

Many folks prefer writing different sections of the paper in separate tex files and including them in the main document using the `include` directive. This has several advantages:
1. Coauthors often feel comfortable working on their individual sections.
2. Makes versioning a little easier.
3. Navigating is less painful.

There are situations where merging those sections into a single document is needed. For example, when some publications ask you to limit the number of files. 
After a little bit googling, [this](http://mirrors.ctan.org/support/latexpand/latexpand) good old perl script seems to get the job done. To merge multiple sections run

```sh
    perl latexpand main.tex > merged.tex
```