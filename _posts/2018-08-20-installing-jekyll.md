---
layout: post
author: psuryan
---
The simplest way to install Jekyll is from [Homebrew](https://brew.sh/).
```sh
brew update
brew install rbenv
ex -sc '1i|export PATH=$HOME/.rbenv/bin:$HOME/.rbenv/shims:/usr/local/bin:$PATH' -cx ~/.bash_profile
rbenv local 2.5.3
gem install jekyll
gem install bundler
```
