---
layout: post
title:  "Cleaning up stale git refs for fun and profit."
date:   2016-10-07 16:24:40
categories: git
---
So you go to pull in changes from a remote repository and it gets stuck trying to `git pull`.

{% highlight shell %}
[project] git pull
error: Ref refs/remotes/origin/feature-branch is at 8bd72135a757cead25f5802497cba2d67f1f34c6 but expected 01bee1509bfa1db05a2160afac1c0798d2b4a505
error: Cannot lock the ref 'refs/remotes/origin/feature-branch.
From ssh://repo.company.com:7999/~user/project
 ! 01bee15..4799efd  feature-branch -> origin/feature-branch  (unable to update local ref)
 {% endhighlight %}

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
