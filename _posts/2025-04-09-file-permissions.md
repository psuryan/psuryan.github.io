---
layout: post
title: Display File Permissions in Numeric Format
date: 2025-04-09
category: productivity
author: 
tags: [ssh, linux]
summary: 
---

When configuring SSH keys, it's crucial to set the correct permissions on the `.ssh` directory and its contents. Incorrect permissions can prevent SSH from working properly.

Here's a handy command to check file permissions in **numeric format** (like `0700`, `0600`, etc.), which is especially useful when setting up your SSH directory:

```sh
stat -c "%a %n" ~/.ssh ~/.ssh/*
```

This may produce an output like the following if permissions have been set correctly.

```sh
700 /home/user/.ssh
644 /home/user/.ssh/authorized_keys
600 /home/user/.ssh/id
644 /home/user/.ssh/id.pub
```