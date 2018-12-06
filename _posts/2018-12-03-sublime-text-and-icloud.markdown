---
title: Sublime Text and iCloud
layout: post
category: Blog-meta
tags: [blog, jekyll, sublimetext, icloud]
---
Many Plugins such as Jekyll don't really understand the configuration paths if they are located on the iCloud Drive (com~apple~CloudDocs). I have found it easier to just create a symlink in my local drive to the iCloud Drive like the following

```sh
/Users/$USER/Library/Mobile\ Documents/com~apple~CloudDocs/SublimeText/projects/project_name alias_project_name
```

So that, my Jekyll configuration looks like this

```json
{
    ...
    "settings":
    {
        "Jekyll":   
        {
            "jekyll_posts_path": "<local_path>/alias_blog/_posts",
            "jekyll_drafts_path": "<local_path>/alias_blog/_posts/_drafts",
            "jekyll_templates_path": "<local_path>/alias_blog/_posts/_layouts",
            ...,
        }
    }
}
```

Also, following [this](https://gist.github.com/elilien/df990641b0a1b8e4a179), I have moved all the sublime configuration to the iCloud so that I can sync them between the macs.

```sh
mkdir -p /Users/$USER/Library/Mobile\ Documents/com~apple~CloudDocs/SublimeText/sync/
cd ~/Library/Application\ Support/Sublime\ Text\ 3/
mv Installd\ Packages /Users/$USER/Library/Mobile\ Documents/com~apple~CloudDocs/SublimeText/sync/
ln -s /Users/$USER/Library/Mobile\ Documents/com~apple~CloudDocs/SublimeText/sync/Installed\ Packages
mv Packages /Users/$USER/Library/Mobile\ Documents/com~apple~CloudDocs/SublimeText/sync/
ln -s /Users/$USER/Library/Mobile\ Documents/com~apple~CloudDocs/SublimeText/sync/Packages
```
