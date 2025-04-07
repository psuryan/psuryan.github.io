---
layout: post
title: Who Changed This Module? Get a Quick Git CSV Log
date: 2025-03-24
category: productivity
author: 
tags: [git]
summary: 
---

Need to see who contributed to a specific folder or module in your codebase? Here's a quick Git command that gives you a clean, CSV-style output:

```sh
git log --pretty=format:'%h,%ad,%an,"%s"' --date=short -- path/to/module
```

Example, 
```sh
git log --pretty=format:'%h,%ad,%an,"%s"' --date=short -- my_app/data_loader
```

```csv
a1b2c3d,2024-11-02,Alice Johnson,"Refactored batch loading logic"
d4e5f6g,2024-10-20,Bob Smith,"Added support for CSV files"
h7i8j9k,2024-09-10,Alice Johnson,"Initial commit for data_loader"
``

Quick, clean, and super helpful. 