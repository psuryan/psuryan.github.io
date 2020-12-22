---
layout: post
title: Embed Pure HTML Inside a Jekyll Blog
date: 2020-12-21
category: Blog-meta 
tags: [blog, jekyll, html]
---

There are many instances where we would like to include an entire HTML page inside a Jekyll blog. This is usually done using the Jekyll's `include` [directive](https://jekyllrb.com/docs/includes/).
However for it to work, the included page has to be inside the `_includes` directory. There is also a `include_relative` directive, whose documentation is confusing at best. Also these `include*` mechanisms 
fail if a sufficiently complex HTML page (such as [Tiddlywiki]({% post_url 2020-12-05-Tiddlywiki %}) ) were to be included. 
The following solution which just uses a simple iFrame seems work work rather well:  

1. Create a directory in the root of the blog with some name, say `files`
2. Drop the file to be included in that directory, say [`example.html`](/files/example.html).
3. Add a code snippet similar to the below in a post.


{% raw %}
```html
<div id="included">
  <iframe height="500" width="800" scrolling="yes"
    src="/files/example.html"
    frameborder="no" allowtransparency="true" allowfullscreen="true">
  </iframe>
</div>
```
{% endraw %}

The output should look like the below.
<div id="included">
  <iframe height="500" width="800" scrolling="yes"
    src="/files/example.html"
    frameborder="no" allowtransparency="true" allowfullscreen="true">
  </iframe>
</div>