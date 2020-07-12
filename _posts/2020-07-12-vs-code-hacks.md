---
title: VS Code Hacks
layout: post
category: Tips
tags: [vscode]
---
VS Code doesn't seem to have a keyboard shortcut for switching between editor and terminal windows. This is typical of the Electron JS apps [don't seem to pay too much attention](https://daringfireball.net/2018/12/electron_and_the_decline_of_native_apps) to ergonomics. [This Stackoverflow answer](https://stackoverflow.com/a/43012779) might just be the best solution for the problem:
```
// Toggle between terminal and editor focus
{ "key": "ctrl+`", "command": "workbench.action.terminal.focus"},
{ "key": "ctrl+`", "command": "workbench.action.focusActiveEditorGroup", "when": "terminalFocus"}
```