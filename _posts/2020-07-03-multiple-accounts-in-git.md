---
title: Multiple Git Accounts
layout: post
category: productivity
tags: [git]
---
Often times people have two GitHub accounts - one for work and personal. Good post on how to manage these accounts [here](https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574).
As mentioned in one of the comments in the same post, it is also important to [configure the ssh-agent](https://superuser.com/questions/272465/using-multiple-ssh-public-keys) to make this work.

And in case one gets mixed up with the two ids (before making the above change), [this](https://stackoverflow.com/a/30737248) StackOverflow answer provides a way to clean it up.
If you correctly implement the above steps, your ssh config will look like the following
```
#Default GitHub
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_rsa
    IdentitiesOnly yes
Host github-<COMPANY>
    HostName github.<COMPANY>.com
    User git
    IdentityFile ~/.ssh/id_rsa_<COMPANY>
    IdentitiesOnly yes
```
In addition to the above steps, if there are any repositories in the your company's Git that you have already checked out and after making the above changes, you would need to update them as well. 
1. The typical `remote.origin.url` for a repo looks like `git@github.<COMPANY>.com:<ORG_OR_USER/PROJECT_NAME>.git`. Change this to the correct URL
`git remote set-url origin git@github-<COMPANY>:<ORG_OR_USER/PROJECT_NAME>.git`
this will result the changed config `remote.origin.url=git@github-<COMPANY>:ORG_OR_USER/<PROJECT_NAME>.git`
2. Change the email config to the correct email address `git config --local user.email <your_email>@<COMPANY>.com` if it is messed up due to the multiple accounts.