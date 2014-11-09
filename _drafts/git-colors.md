---
layout: post
title: Colors for command line git.
date: 2014-11-9 11:00:00
categories: git hacking programming
---
Using **git** from the command is great, but with out-of-the-box settings it can be more of a chore and harder on your eyes than it needs to be. In this post we'll present some tricks that will make command line git more efficient and ejoyable.


### **Step 1: Create a .bash_profile**

Some of the following configurations will require you to add to a file called .bash_profile, which is used to configure Git Bash if you’re using Windows, or the terminal if you’re using Mac or Linux. (If your terminal is using a different shell than bash, than many of the following instructions will not work. However, bash is the default on both Mac and Ubuntu.) Note: Since this file has a period at the beginning of its name, it is called a hidden file and will not appear in most file system navigators. To create this file:

- Navigate to your home directory `cd [ENTER]`
- Create a new file named .bash_profile `touch .bash_profile [ENTER]`
- Use `ls -a`, which shows hidden files, to confirm your file has been created.

Alternatively, if you're interested, you can use the .bash_profile we used when filming this course. To do so:

Download bash_profile_course from the Downloadables section.
Move the file to your home directory.
Rename the file to .bash_profile, including the period at the beginning.
If you already have a .bash_profile, you don’t need to create a new one. You can add the content from the example .bash_profile if you would like.

### **Step 2: Setting up tab completion**

Setting up tab completion allows you to type the first few characters of a Git command, press tab, and have the rest of the command filled in. In Lesson 2, you’ll also be giving names to some of your commits, and tab completion will allow you to auto complete these names in the same way. Having tab completion set up can make working with Git much more efficient.

To set up tab completion:

Follow the instructions above in the section "Downloading necessary files" to make sure your home directory contains the file git-completion.bash.
Add the line source git-completion.bash to your .bash_profile.