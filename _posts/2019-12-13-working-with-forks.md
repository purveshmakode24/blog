---
layout: post
title:  "Working with Forks?!"
date:   2019-12-13 15:00:00 +0900
categories: posts
read: "8 minutes read"
---

<br/>

Forks are often used in open source development on GitHub. If you are planning on contributing to someone else's project on Github, but don't know how to keep your fork up-to-date then this is the best place to help you get started.

<br/>

#### What is Forking?

A fork is a replica of a repository that you manage. Forks let you make changes to a project without affecting the owner's repository. You can fetch updates from or submit changes to the owner's repository with pull requests. In other words, when we love someone else's repository and would like to have it in our GitHub account, we fork it so that we can work with it separately.

> Note: Here owner's repository refers to the original repository or upstream repository.

<br/>

#### What is a pull request?

Pull requests are the way we contribute to open source or group projects.

For instance, a user Paul forks a repository of Benedict and makes changes to that repository. Now Paul can make a pull request to Benedict, but it’s up to Benedict to accept or decline it. It’s like Paul is saying, “Benedict, would you please pull my changes?!”

<br/>

#### Choose the forked repository you are working on

* Clone your fork:

```
git clone git@github.com:YOUR-USERNAME/YOUR-FORKED-REPO.git	 
```

<br/>

#### Configuring a remote for a fork

Configuring a remote for a fork is often required to [sync changes](#syncing-a-fork) from the original repository to your forked repository. (That's the case when the original repository is not even with the forked repository)

* Add remote from the original repository (owner's/upstream) in your forked repository:

```
cd into/cloned/fork-repo

git remote add upstream https://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git

git fetch upstream
```

<br/>

#### Syncing a fork (Keeping fork up-to-date) {#syncing-a-fork}

Sync a forked repository to keep it up-to-date with the upstream repository.

* Updating your fork from the original repository to keep up with their changes:

```
git pull upstream master
```

At this stage, your forked repository (Local) must have synced with the original repository.
	
> Note: But we can't see this sync in our remote branch. So we have to push these changes from your Local to Remote.
	
* Push all the changes from your Local to Remote:

```
git push origin master
``` 
	
✅ At this stage, your forked repository (both Local and Remote) must have synced with the original repository.

> In case if you're confused with what remote and local in this context really means?! [Following diagram](#fork-and-clone) will help you out:

<img id="fork-and-clone" src="/assets/images/fork-and-clone.png" alt="fork-and-clone" style="max-width: 100%; display: block;
    margin: 0 auto;"/>
<p style="text-align: center">Fig., Workflow: Fork/Sync and Cloning</p> 

<br/>

## Pro Tips 

> If you've basic understanding of how pull request and branches works, these are the best practices you must follow while working with the forked repository:

1. If you want to make some changes into an app, prefer to create feature branches. i.e., Instead of making changes into your forked master-branch, make changes into your Feature-Branch.

2. Keep your remote/local forked master-branch synchronized before creating any Feature-Branch. (This hardly gives you any merged conflict when you make pull request, unless any other user is making the same changes that you are making after your remote/local forked master-branch is synchronized with original branch)
    
    > If that's the case (Got any merge conflicts), you can simply resolve it by removing your conflict code from the feature-branch.
  
3. Keep your local/remote forked master-branch synced with the original master-branch before making any pull requests.

4. Delete the feature branch when pull request is accepted.

> **Original Master Branch**: Owner's/Upstream master-branch from which you forked the repository.
