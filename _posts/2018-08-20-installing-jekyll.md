---
layout: post
author: psuryan
category: Blog-meta
tags: [blog, jekyll]
---
The simplest way to install Jekyll is using [Homebrew](https://brew.sh/) if the operating system is MacOS. Assuming that the Homebrew is already installed, we need make sure that it is up-to-date. 

Also, Jekyll is built on top of Ruby. We might not want to mess around with the Ruby installation that comes with the MacOS. So it is preferably to install `rbenv` first.  
```sh
brew update
brew install rbenv
ex -sc '1i|export PATH=$HOME/.rbenv/bin:$HOME/.rbenv/shims:/usr/local/bin:$PATH' -cx ~/.bash_profile
rbenv local 2.5.3
gem install jekyll
gem install bundler
```
