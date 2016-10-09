---
layout: post
title:  "Cleaning up stale git refs for fun and profit."
date:   2016-10-07 16:24:40
categories: git
---
So you `git fetch` some changes from a remote repository and it gets stuck trying to `git pull`. 

{% highlight shell %}
[project] git pull
error: Ref refs/remotes/origin/feature-branch is at 8bd72135a757cead25f5802497cba2d67f1f34c6 but expected 01bee1509bfa1db05a2160afac1c0798d2b4a505
error: Cannot lock the ref 'refs/remotes/origin/feature-branch.
From ssh://repo.company.com:7999/~user/project
 ! 01bee15..4799efd  feature-branch -> origin/feature-branch  (unable to update local ref)
 {% endhighlight %}

This happens to me with stash somewhat regularly and I end up running these two commands to clean up refrences on the local and remote.

{% highlight shell %}
[project] git gc --prune=now
Counting objects: 90724, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (33738/33738), done.
Writing objects: 100% (90724/90724), done.
Total 90724 (delta 50066), reused 89191 (delta 48831)

[project] git remote prune origin
{% endhighlight %}

Now that everything is nice and clean, `git pull` should work like new again.

{% highlight shell %}
[project] git pull
From ssh://repo.company.com:7999/~user/project
   01bee15..4799efd  feature-branch -> origin/feature-branch
Updating 88b7cb1..fce7d93
Fast-forward
 file.extension                                    |    132 +-
 file.extension                                    |      2 +-
 client-app/.babelrc                               |      2 +-
 client-app/.eslintrc                              |     21 +-
 ...
{% endhighlight %}

Mmm, new repo smell. See the issue on [Stack Overflow][so-page] for more information.

[so-page]:  http://stackoverflow.com/a/7348934

