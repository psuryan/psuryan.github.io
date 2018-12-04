---
title: Sublime Text for Jekyll based blog
layout: post
---
It is possible to create a [Jekyll] based blog and maintain it with just terminal based tools (`vi` etc.). But having a decent text editor such as [Sublime Text] makes this much less of a chore. Assuming that you have both Jekyll and Sublime Text installed already, here is how you can configure Sublime Text.


## Jekyll Plug-in ##
Enter [sublime-jekyll], a Jekyll plug-in for Sublime Text. The first step is into install the Sublime Text package manager, `Package Control`. 
    First invoke `Command Palette` by pressing *`↑⌘P`
    Type `Package Control`
    In the drop down, select `Install Package`
    In the next search window type "jekyll" and press `⏎`
Once the plug-in is successfully installed, it is time to configure it. Go to `Project` ➡️ `Edit Project`. It will open a blank file. Update it look something like this.
```json
{
    "folders":
    [
        {
            "follow_symlinks": true,
            "path": "<path_to_the_repo_of_blog>"
        }
    ],

    "settings":
    {
        "Jekyll":   
        {
            "jekyll_posts_path": "<path_to_the_repo_of_blog>/_posts",
            "jekyll_drafts_path": "<path_to_the_repo_of_blog>/_drafts",
            "jekyll_templates_path": "<path_to_the_repo_of_blog>/_layouts",
            "jekyll_auto_find_paths": true,
        }
    }
}
```
Save the file with a name like `blog.sublime-project`. Once the file is saved, you should be able to see all your repository folders (created earlier in command line by Jekyll) appear on the left panel of the editor if you have the show side bar enabled from the `View` menu. Sublime calls this a `Project`. The plug-in allows one to create drafts and promote / publish them (and a lot more [capabilities]) from Sublime Text. The Jekyll [tutorial] that I used to create the blog didn't have placeholders for drafts. I manually created a folder called `_drafts` in my repository.  

## Build System ##
The next step is to create a [build system] and attach it to the `Project`. To do this, we can add the following snippet to the configuration above
```json
    "build_systems": [{
        "name": "Jekyll",
        "cmd": "<some_path>/jekyll-build-script.sh",
        "shell": true,
        "encoding": "UTF-8",
        "working_dir": "<path_to_the_repo_of_blog>"
    }]
```
The `jekyll-build-script.sh` contains the commands that you would normally use to `build` and `serve` in command line.

```sh
echo "Start building..."
rbenv local 2.5.3
echo $1
cd "$1"
/Users/$USER/.rbenv/shims/jekyll serve -t
```
Once this is setup, launching the local server is as easy as hitting `⌘ + b` in Sublime Text.

[Jekyll]:https://jekyllrb.com
[Sublime Text]: https://www.sublimetext.com
[sublime-jekyll]: https://packagecontrol.io/packages/Jekyll
[tutorial]: https://jekyllrb.com/docs/step-by-step/01-setup/
[build system]: https://www.sublimetext.com/docs/3/build_systems.html
[capabilities]: https://sublime-jekyll.readthedocs.io/en/latest/commands.html