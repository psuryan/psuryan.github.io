---
title: Sublime Text and Markdown
layout: post
category: blog-meta
tags: [sublimetext, markdown]
---
The Sublime Text's support for Markdown is amazing. There are many supported plugins. As suggested in [this article](http://plaintext-productivity.net/2-04-how-to-set-up-sublime-text-for-markdown-editing.html), I found Markdown Editing and Markdown Preview to be the most interesting.

But there can be a potential problem during the installation of Mardown Editing  - after the Plugin is installed, it once you open the "Mardown Settings - User", it displays an error which looks like this

```err
Error loading syntax file "Packages/Markdown/Markdown.sublime-syntax": Unable to read Packages/Markdown/Markdown.sublime-syntax
```

This is usually [due to](https://github.com/SublimeText-Markdown/MarkdownEditing/issues/485) a markdown file that is currently open during the time of installation of the Markdown Editing package. Just close the file and restart the Sublime Text and the error goes away.