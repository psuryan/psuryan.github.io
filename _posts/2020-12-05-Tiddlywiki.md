---
layout: post
title: Tiddlywiki 
date: 2020-12-05 23:12
category: Tips
tags: [tiddlywiki]
summary: 
---
[Tiddlywiki](tiddlywiki.com) is an amazing piece of software. It promises being future proof as a feature:
> If you're starting to use TiddlyWiki at the beginning of your career you can be confident that it will carry you through to retirement.


It is a single HTML file with no additional dependencies after all! But don't let that simplicity fool you - it is packed with [features](https://tiddlywiki.com/#Features) from audio support to encryption. 
And then there are [tons of](https://tiddlywiki.com/static/Plugins.html) [plugins](https://tid.li/tw5/plugins.html) contributed by the community. When compared to the [many](https://getnotion.com/) [paid](https://roamresearch.com/) solutions for knowledge organization, it is quite powerful but costs nothing!
Getting started with Tiddlywiki could be quite changing. But [this YouTube video tutorial](https://youtu.be/ZMGpAW0z_Bo) is very helpful.

You can also use the Tiddlywiki for collaborative editing using the awesome [TiddlyServer](https://arlen22.github.io/tiddlyserver/) project. There are docker wrappers available such as [this one](https://github.com/djmaze/tiddlywiki-docker). 
To start a Tiddlywiki server follow the steps below on your local machine or a server instance.

```sh
    docker pull mazzolino/tiddlywiki
    mkdir your-wiki-name
    docker run -d -p 8080:8080 -v $(pwd)/<your-wiki-name>:/var/lib/tiddlywiki mazzolino/tiddlywiki
``` 

The folder `your-wiki-name` will contain the contents of your Tiddlywiki. Navigate to `http://<server-name>:8080` to get started on setting up the wiki.