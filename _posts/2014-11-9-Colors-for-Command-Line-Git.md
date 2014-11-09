---
layout: post
title: Colors for command line git.
date: 2014-11-9 11:00:00
categories: git hacking programming
---
**Using git** from the command is great, but with out-of-the-box settings it can be more of a chore and harder on your eyes than it needs to be. In this post I'll present some tricks that will make command line git more efficient and ejoyable.

**Note:** Most of the content of this post came from the **How to Use Git and GitHub** course on [Udacity](http://www.udacity.com). I have reproduced it here because *reasons*. Mainly:

- I want to save this info somewhere I can reference it in the future
- It's good practice for writing a blog post and getting comfortable with Markdown and Jekyll
- I'm using tools like git and GitHub in the creation of my blog - so good practice there too
- Reviewing/reflecting on this information will solidify the concepts for me, which means I probably won't even need to reference this post in the future--ironical, huh?

### **Step 1: Create a .bash_profile**

Some of the following configurations will require you to add to a file called .bash_profile, which is used to configure Git Bash if you’re using Windows, or the terminal if you’re using Mac or Linux. (If your terminal is using a different shell than bash, than many of the following instructions will not work. However, bash is the default on both Mac and Ubuntu.)

**Note:** Since this file has a period at the beginning of its name, it is called a hidden file and will not appear in most file system navigators. To create this file:

- Navigate to your home directory `cd [ENTER]`
- Create a new file named .bash_profile `touch .bash_profile [ENTER]`
- Use `ls -a`, which shows hidden files, to confirm your file has been created.

Alternatively, you can download an example bash profile by clicking [here.]({{ site.url }}/downloads/bash_profile_example)
Move the file to your home directory and rename it to .bash_profile, including the period at the beginning.
If you already have a .bash_profile, you don’t need to create a new one. You can add the content from the example bash profile if you would like.

### **Step 2: Setting up tab completion**

Setting up tab completion allows you to type the first few characters of a Git command, press tab, and have the rest of the command filled in. In Lesson 2, you’ll also be giving names to some of your commits, and tab completion will allow you to auto complete these names in the same way. Having tab completion set up can make working with Git much more efficient.

To set up tab completion:

1. Download [this git-completion.bash file](https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash).
1. Add the line `source git-completion.bash` to your .bash_profile.

### **Step 3: Modifying your prompt**

Every time you type a command, the symbol that appears before you type is called the prompt. Many people who use Git like to modify their prompt to show what commit they’re currently on, and whether they have any uncommitted changes.

The example .bash_profile above already contains a customized prompt. If you’re not using this profile and you don’t already have a custom prompt, I recommend including the name of the directory you’re in, followed by the commit you have checked out with a * if you have uncommitted changes. I also recommend using a bright color, such as blue, so that your prompt will stand out from the commands that you run. To get a prompt like this:

Download the file [git-prompt.sh](https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh) and place it in your home directory.

Add the following lines to your .bash_profile: 

	source git-prompt.sh 
	export GIT_PS1_SHOWDIRTYSTATE=1 
	export PS1="\[\033[01;34m\]\W\$(__git_ps1)$ \[\033[00m\]"

It's not necessary to understand how these magic-looking lines work. Even experienced Unix programmers usually copy and paste bash prompt strings rather than writing them from scratch. If you're curious though, here is an explanation of what kinds of things a bash prompt can contain and how to configure it.