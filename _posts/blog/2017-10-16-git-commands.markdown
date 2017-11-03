---
layout: post
title:  "The Essencial Git Commands"
date:   2017-10-16 23:00:00 +0800
categories: blog
id: 45
---

Git is nowadays almost one of the most used tools for a professional Web developer. However, there are a lot of git commands at your desposal. I here list the most used and also the most useful commands from my own developing experiences.

* git add
This is for staging files.
* git commit -m
This is for commiting or making a snapshot of your staged files.
* git commit -am
This is for auto commiting files even without staging them first.
* git diff
This is for displaying the change. You can even display the changes between different branches.
* git diff --staged
Display the difference between the staged and unstaged.
* git log
This is for showing the log messages of operations.
* git log --oneline
Logging out concise messages.
* git log --graph
Logging out messages using graph form.
* git log --oneline --graph --all --decorate
logging out all the messages using more user-friendly format.
* gitk
Opening the GUI interface for git.
* gitk --all
* git branch
Showing all available branches for the current repository.
* git branch branch-name
Creating a new branch called 'branch-name'.
* git checkout branch-name
Change to the branch called 'branch-name'.
* git merge branch-name
Merge the branch 'branch-name' to the current branch.
* git branch -d branch-name
Delete a branch called 'branch-name'.
* git rebase branch-name
merge 'branch-name' to the state before changes
* git remote -v
Display the connected remote repositories.
* git remote add origin https://github.com/xxxx.git
Add the remote repository of *github* named *xxxx*.
* git push -u origin master
Push the local repository to the default remote repository and saving the configuration parameters for later easier pushing.
* git push
Push the local repsository to the default remote repository.
* git pull
Pull the default remote repository to the local folder.
* git clone
Clone the default remote repository to the local folder.
* git fetch
Fetch from remote repository but not merge locally.

Besides the above mentioned *git* commands, there are other more friendly ways to use git. They are using *git* in the browser, using *git* by a GUI application, such as *Github Desktop* and using *git* in the IDEs or code editors (most code editors and IDEs have git being integrated).

More information about *git* and *github* can be found in [git Website][git] and [github][github].

[git]: https://www.git-scm.com
[github]:   https://www.github.com