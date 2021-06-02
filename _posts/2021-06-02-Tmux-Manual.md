---
title: Tmux Manual
format: post
tags:
  - CS Skill
  - Tmux
---

# Tmux Manual

[toc]



## What is Tmux

From Wikipedia 

> Tmux is an open-source terminal multiplexer for Unix-like operating systems. It allows multiple terminal sessions to be accessed simultaneously in a single window. It is useful for running more than one command-line program at the same time.

There are not much commands need to talk about, just need to spend some time to learn about the keyboard shortcuts.

<img src="../assets/img/CleanShot 2021-06-02 at 16.21.26@2x.png" alt="CleanShot 2021-06-02 at 16.21.26@2x" style="zoom:50%;" />

## Sessions, windows & panels

When you type `tmux` in command line, you start a tmux session and in each tmux session, you can have multiple windows and in each window you can have multiple panels, so we are actually working in a panel.

### Windows

In a tmux session we can create a window by typing `Ctrl+b c` . Now we can see a *0:zsh\** at bottom, *0* represents the number of this window, and *\** represents the active window.

<img src="{{site.baseurl}}/assets/img/CleanShot 2021-06-02 at 16.29.23@2x.png" alt="CleanShot 2021-06-02 at 16.29.23@2x" style="zoom:50%;" />

We can use `Ctrl+b ,` to change the name of this window, now it becomes *Genius* rather than *zsh*.

<img src="{{site.baseurl}}/assets/img/CleanShot 2021-06-02 at 16.31.57@2x.png" alt="CleanShot 2021-06-02 at 16.31.57@2x" style="zoom:50%;" />

We can switch between different windows by using these shortcuts:

- ctrl+b p (previous的首字母) 切换到上一个窗口。
- ctrl+b n (next的首字母) 切换到下一个窗口。
- ctrl+b 0 切换到0号窗口，依次类推，可换成任意窗口序号
- ctrl+b w (windows的首字母) 列出当前session所有窗口，通过上、下键切换窗口
- ctrl+b l (字母L的小写)相邻的窗口切换

At last, use `Ctrl+b &` to close the current window.

### Panels

`Ctrl+b "` to split the horizontally

<img src="{{site.baseurl}}/assets/img/CleanShot 2021-06-02 at 16.35.26@2x.png" alt="CleanShot 2021-06-02 at 16.35.26@2x" style="zoom:50%;" />

`Ctrl+b %` to split vertically

<img src="{{site.baseurl}}/assets/img/CleanShot 2021-06-02 at 16.36.37@2x.png" alt="CleanShot 2021-06-02 at 16.36.37@2x" style="zoom:50%;" />

Switching around panels:

- ctrl+b o 依次切换当前窗口下的各个窗格。
- ctrl+b Up|Down|Left|Right 根据按箭方向选择切换到某个窗格。
- ctrl+b Space (空格键) 对当前窗口下的所有窗格重新排列布局，每按一次，换一种样式。
- ctrl+b z 最大化当前窗格。再按一次后恢复。

There is an alternative way to switch, that is to type `ctrl+b q` and tmux will show the number of different panels, then type the corresponding number before it disappears(you have to be very quick).

<img src="{{site.baseurl}}/assets/img/CleanShot 2021-06-02 at 16.39.44@2x.png" alt="CleanShot 2021-06-02 at 16.39.44@2x" style="zoom:50%;" />

Last, use `ctrl+b x` to close current active panel.

# Advanced

## Oh-my-tmux config

A powerful tmux configuration to make tmux beautiful and productive.

[oh-my-tmux](https://github.com/gpakosz/.tmux)

## Enable mouse scrolling

In tmux session enter `ctrl+b :` to enter commands:

> setw -g mode-mouse on

You can also put this in .tmux.config to make it effective every time when you open tmux.
