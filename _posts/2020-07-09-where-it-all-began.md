---
layout: post
title:  "Working with Forks?!"
date:   2019-12-25 15:00:00 +0900
categories: posts
read: "10 minutes read"
---

Forks are often used in open source development on GitHub.  If you are planning on contributing on someone else's project on github, but don't know how to keep your fork up-to-date then this is the best place to help you get started.

### What is Forking?
A fork is a copy of a repository that you manage. Forks let you make changes to a project without affecting the original repository. You can fetch updates from or submit changes to the original repository with pull requests. In other words when we love someone’s repository and would like to have it in our GitHub account, we fork it so that we can work with it separately.


### What is a pull request?

Pull requests are the way we contribute to group projects or open source projects.

For instance, a user Alice forks a repository of Bob and makes changes to that repository. Now Alice can make a pull request to Bob, but it’s up to Bob to accept or decline it. It’s like saying, “Bob, would you please pull my changes?”

### Choose the forked repository you are working on

* Clone your fork
	```
	git clone git@github.com:YOUR-USERNAME/YOUR-FORKED-REPO.git
    ```

### Configuring a remote for a fork
Configuring a remote for a fork is often required to [sync changes](#) from original repository to your forked repository. (That's the case when the original repository (owners) is not even with the forked repository)

*  Add remote from original repository in your forked repository: 
	```
	    cd into/cloned/fork-repo
	    git remote add upstream git://github.com/ORIGINAL-DEV-USERNAME/REPO-YOU-FORKED-FROM.git
	    git fetch upstream
	```
### Syncing a fork (Keeping fork up-to-date)
Sync a fork of a repository to keep it ==up-to-date== with the upstream repository.
* Updating your fork from original repo to keep up with their changes:
	```
	    git pull upstream master
	```

	At this stage your forked repository (Local) must be synced with original repository.
	> Note: But we can't see this sync in our remote branch.  So we have to push this changes from your Local to Remote
	
* Push all the changes from Local to Remote:
	```
	    git push origin master
	``` 
:white_check_mark: At this stage your forked repository (both Local and Remote) must be synced with the original repository.

> In case if you're confused with what remote and local in this context really means?! [Following diagram](#) will help you out


![fork and clone](/assets/images/fork-and-clone.png)


## Pro Tips 

> #### If you have basic understanding of how pull request and branches works, these are the best practices you must follow while working with the forked repository:

#####
1) If you want to make some changes into an app, prefer to create feature branches. i.e., Instead of making changes into your forked master-branch, make changes into your Feature-Branch.

#####
2) Keep your remote/local forked master-branch synchronized before creating any Feature-Branch. (This hardly gives you any merged conflict when you make pull request, unless any other user is making the same changes that you are making after your remote/local forked master-branch is synchronized with original branch)
    
    > #### If that's the case (Got any merge conflicts), you can simply resolve it by removing your conflict code from the feature-branch)
  
#####  
3) Keep your local/remote forked master-branch synced with the original master-branch before making any pull requests.

4) Delete the feature branch when pull request is accepted.

  > **Original Master Branch**: Owner's/Upstream master-branch from which you forked the repository.

    
    
