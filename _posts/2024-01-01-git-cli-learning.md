---
layout: post
title: "Git CLI Learning"
date: 2024-01-01
categories: [learning, github]
tags: [git, cli, tutorial]
toc: true
description: "A comprehensive guide to learning Git CLI commands, covering basic operations, branching, merging conflicts, pushing to GitHub, and creating Jekyll posts."
---

## Learning

<br>
Initial commit - 19:52 <br>
Finish time - 23:28
<br>
<br>

<!-- CODE BLOCK -->
{% highlight ruby %}
Git show
#this shows audit trail (commit history)
{% endhighlight %}

[Committing local copy to git](https://stackoverflow.com/questions/36160779/git-added-wrong-folder-source)
￼

[Git and GitHub Tutorial for Beginners](https://www.youtube.com/watch?v=tRZGeaHPoaw)
45 min

<br>
## Basic commands

<!-- CODE BLOCK -->
{% highlight ruby %}
Git init
#initialises the repo as a git repo

Git checkout -b gh-pages
#Swaps to the gh-pages branch

Git diff
#this shows the difference between staging and current committed

Git rm “name of file.txt”
#this removes the file from your local pc

Git restore “name of file.txt”
#this will restore the file which was deleted

Git mv “name of file” “new name of file”
#to update the name of a file

Git commit -m “message to commit”
#committing the name change

Git log —online
#this shows you all commits but on one line

Git log -p
#shows a history of all of the different changes within the most recent commit
{% endhighlight %}

<br>
## Branches

<!-- CODE BLOCK -->
{% highlight ruby %}
Git branch name
#this will create a new branch with the name “name”

Git branch
#This will show you available branches you know which branch you’re in as it’s green and has a *

Git switch branch_name
#switches to another branch

Git commit -a -m “message”
#commits to the currently selected branch with the message entered

Git switch main
#switches back to the main branch

Git merge -m “message” branch_name
#this will merge the changes made in the branch_name with the main branch

Git branch -d branch_name
#this will delete the branch_name branch
{% endhighlight %}

<br>
## Branch merge with conflicts

<!-- CODE BLOCK -->
{% highlight ruby %}
Git switch -c branch_name
#creates a new branch then also switches to it
{% endhighlight %}

<br>
## Pushing changes to GitHub

<!-- CODE BLOCK -->
{% highlight ruby %}
git remote add origin https://github.com/Jamie-Kent/personal_blog.git

Git branch -M main

Git push -u origin main
{% endhighlight %}

<br>
10 min
<br>
[Updates were rejected because the tip of your current branch is behind its remote counterpart](https://stackoverflow.com/questions/39399804/updates-were-rejected-because-the-tip-of-your-current-branch-is-behind-its-remot)

<!-- CODE BLOCK -->
{% highlight ruby %}
#Could not push using 
Git push -u origin gh-pages

#Pushed using
Git push -f origin gh-pages
{% endhighlight %}

<br>
21:45 - 21:58
<br>
[Link broken as it directs to personal_blog after I changed the base url](https://jamie-kent.github.io/personal_blog/jekyll/update/2023/12/27/welcome-to-jekyll.html)


<!-- CODE BLOCK -->
{% highlight ruby %}
Git push -all
#pushes through all branches

Git fetch
#fetches all changes from cloud source

Git merge
#merges all fetched changes into the your local repo

Git pull
#this combines both git fetch and also git merge
{% endhighlight %}


<br>
## Creating posts
21:58 - 22:12
[Writing Posts | Jekyll - Static Site Generator | Tutorial 6](https://www.youtube.com/watch?v=gsYqPL9EFwQ&list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB&index=6)



22:18 - 22:38
[Creating Pages | Jekyll - Static Site Generator | Tutorial 8](https://www.youtube.com/watch?v=1na-IWfv08M&list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB&index=8)


22:38 - 22:52
[Writing Posts | Jekyll - Static Site Generator | Tutorial 6](https://www.youtube.com/watch?v=gsYqPL9EFwQ&list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB&index=6)

22:52-23:19
<br>
Writing up learning notes in markup

<br><br>

**Restoring a removed file** <br>

<!-- CODE BLOCK -->
{% highlight ruby %}
git rm "_drafts" -r
#removed my-first-draft.markdown

git status
#checked status of staged files

git restore --staged _drafts/my-first-draft.markdown
#the file then appeared in the source control section
{% endhighlight %}

<br>

**Untracking all files then retracking all files** <br>

<!-- CODE BLOCK -->
{% highlight ruby %}
git rm -r --cached .
git add .
#retracking all files
{% endhighlight %}

