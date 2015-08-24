# GitHub Collaboration

## Set Up Your System

To use GitHub, you'll have to prepare your work environment first. This part only has to be done once.

1. [Create a GitHub account](https://github.com/)

1. Install git on your computer using `gem install git` or follow the instructions on [githowto.com](http://githowto.com)

1. Configure git on your computer. Make sure these correspond with your GitHub account settings.
```
git config --global user.name "Your Name"
git config --global user.email "your_email@whatever.com"
```

1. Work through [GitHub's introductory tutorial](https://try.github.io) to learn the basics of version control with git.
Keep a bookmark to the [Git Cheat Sheet](http://byte.kde.org/~zrusin/git/git-cheat-sheet-medium.png) for reference.

## Get a Project onto Github

We'll presume you have a project you've been working on that you'd like to version control,
but ideally you'd follow this process on an empty directory before you begin development.

1. ```cd``` to your project's root directory.

1. Initialize a git project in this directory with `git init`

1. Add all files in your project to your local git repository with `git add .`

1. Commit your project’s current state to git version control with `git commit –m "Initial commit"`

1. Go to your GitHub account and create a repo for your project to reside in by clicking the icon in the upper-right corner.

1. When you create the repo, you will be redirected to notes for connecting your local machine’s repo to your GitHub repo:
```
git remote add origin git@github.com:github-handle/repo-name.git
```

1. Push your commits to the remote repository with
```git push -u origin master```

## Basic Version Control of Your Repo

1. As you work on your project, add new files and modifications to your repo with `git add .` or `git add filename`, then commit changes with `git commit –m "commit notes"`.
**Replace "commit notes" with a useful, self-explanatory summary of your changes.**

1. The `git push –u origin master` you used to get your project onto GitHub attaches your local master branch to GitHub's,
so now a simple `git push` will push your new commits to your GitHub repo.

1. You can push whenever you want. If you have made several commits without pushing, they will all go at once when you do.

1. Use `git log` to see a history of your commit changes and `git status` to see the status of your present work.

1. Now try doing some more advanced things like reverting, pulling, making new branches, etc by working through some of the attached resources listed at the bottom of the page.

## Forking Existing Repos, Submitting Pull Requests

**Forking** a repo means creating your own copy of someone else's public repository in order to experiment or contribute your own changes.
A **pull request** is a means of alerting the original author that you have changes you'd like merged into the original project.
The owner of the original repository can review your changes and choose whether or not to "pull" them in and make them available to everyone.

1. Go to original author’s repo on GitHub and fork it into a repo on your account.

1. Clone your forked repo onto your local computer
```
git clone git@github.com:your-git-handle/reponame.git
```

1. If you get `error: port 22 connection refused`, it’s probably an issue with GitHub not being able to find your SSH key. Here’s a solution: http://stackoverflow.com/questions/7953806/github-ssh-via-public-wifi-port-22-blocked

1. Create a new branch for your repo. This is where you will make your changes. We will work from a new branch, leaving the original master branch unchanged. This will later allow us to submit a pull request without getting merge conflicts with the original branch. The new branch we will create will start off identically to the master branch:
```
git checkout origin -b <new-branch-name>
```

1. We are now working on the <new-branch-name> branch. Edit, add, delete the project files as you see fit in this branch.

1. Commit changes

1. Attach your new branch to your GitHub repo with
```
git remote add upstream https://github.com/YourGitHandle/Reponame.git
```

1. Push your commit

1. Go to your GitHub repo. Go to your <new-branch-name> branch. Submit the pull request.

1. The original author may now authorize the pull request. Once authorized, the author can now merge the new branch into the master branch with:
```
git checkout <new-branch-name>
git merge master
```

# Useful Resources

* [github.com](https://github.com)
* [githowto.com](http://githowto.com)
* [Try Git](http://try.github.io)
* [Git Cheat Sheet](http://byte.kde.org/~zrusin/git/git-cheat-sheet-medium.png)
* [Forking a GitHub Repo](https://help.github.com/articles/fork-a-repo)
