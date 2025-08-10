# 1. Setup

In order to contribute to a GitHub project, you will need two things: a GitHub *Source* Forked Repo (upstream) and *Your* Fork (origin) project.

## :running: Activities

Follow along with the activities below to get yourself ready for the rest of the walkthrough.


### 1 - Fork a Source Repository

__All Team Members__

Fork the source repository:
   1. Visit https://github.com/source-username/repository-name.
   2. Click the "fork" button, and choose your personal GitHub account if prompted.
   2. Check that you know are working in your own fork project, named https://github.com/your-username/repository-name.

---

:cop: :raised_hand: - Please wait until everyone has caught up.

:construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction:

---

### 2 - Clone your Fork

__All Team Members__

Clone this project to your local machine:
```sh
$ cd ~/my/parent/directory
$ git clone https://github.com/your-username/repository-name.git
# clone the fork repository from GitHub

$ cd repository-name
# change working directory to the cloned repository
```

View existing remotes:
```sh
$ git remote
origin

$ git remote -v
origin https://github.com/your-username/repository-name.git (fetch)
origin https://github.com/your-username/repository-name.git (push)
```

You should see an `origin` remote that points to your fork GitHub project:
```sh
$ git remote show origin
* remote origin
  Fetch URL: https://github.com/your-username/repository-name.git
  Push  URL: https://github.com/your-username/repository-name.git
  HEAD branch: main
  Remote branches:
    develop tracked
    main  tracked
  Local branch configured for 'git pull':
    main  merges with remote main
  Local ref configured for 'git push':
    main  pushes to main (up to date)
```

View existing branches:
```sh
$ git branch
# show local branches
* main

$ git branch -r
# show remote branches
origin/HEAD -> origin/main
origin/develop
origin/main

$ git branch -a
# show all branches
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/develop
  remotes/origin/main
```

---

:cop: :raised_hand: - Please wait until everyone has caught up.

:construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction:

---

### 3 - Add Remote for the source GitHub Forked project

__All Team Members__

Add a `upstream` remote:
```sh
$ git remote add upstream https://github.com/source-username/repository-name.git
# add the upstream remote

$ git remote -v
origin https://github.com/your-username/repository-name.git (fetch)
origin https://github.com/your-username/repository-name.git (push)
upstream https://github.com/source-username/repository-name.git (fetch)
upstream https://github.com/source-username/repository-name.git (push)
```

You should see a `upstream` remote that points to the source GitHub Fork repository:
```sh
$ git remote show upstream
* remote upstream
  Fetch URL: https://github.com/source-username/repository-name.git
  Push  URL: https://github.com/source-username/repository-name.git
  HEAD branch: main
  Remote branches:
    develop new (next fetch will store in remotes/upstream)
    main  new (next fetch will store in remotes/upstream)
  Local ref configured for 'git push':
    main  pushes to main (up to date)
```

Maintainers will need to create branches and push directly to the source repository.

All team members will need to pull changes from the source repository in order to branch from for feature branches.

Fetch branch data from the `origin` remote:
```sh
$ git fetch origin
From https://github.com/your-username/repository-name
* [new branch]      develop    -> origin/develop
* [new branch]      main     -> origin/main

$ git branch -a
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/develop
  remotes/origin/main
  remotes/upstream/develop
  remotes/upstream/main
```

---

:cop: :raised_hand: - Please wait until everyone has caught up.

:construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction:

---

### 4 - Configure Local Branches

__All Team Members__

By now you should have noticed that you do not have a local `develop` branch
```sh
$ git branch
* main
```

Create a `develop` branch that tracks from `origin`'s `develop` branch:
```sh
$ git checkout -b develop --track origin/develop
Branch develop set up to track remote branch develop from origin
```

Notice that viewing the details for the `origin` remote indicates that the local `develop` and `main` branches are configured to push to and pull from the source GitHub repository's branches:
```sh
$ git remote show origin
...
   Local branches configured for 'git pull':
     develop merges with remote develop
     main  merges with remote main
   Local branches configured for 'git push':
     develop pushes to develop (up to date)
     main  pushes to main (up to date)
```

:bulb: The `-vv` flag for the `git branch` command will also show the remote branches that are tracked by your local branches (in brackets):
```sh
$ git branch -vv
* develop 3e03a92 [origin/develop] Create example app
  main  3e03a92 [origin/main] Create example app
```

You should now be ready to move on to the rest of the walkthrough. If you'd like to see the repository you've created on your local machine in GitHub desktop, you can add a repository by choosing a local path.

---

:cop: :raised_hand: - Please wait until everyone has caught up.

:construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction: :construction:

---

## Next

Next we will walk through the process of creating feature branches, publishing changes to GitHub, and making a request to merge changes into the source or other repository using a Pull Request.

[Go](2-feature-branches.md)

## Quick Links

- [Readme](../readme.md)
- [2. Feature Branches](2-feature-branches.md)
- [3. Code Review](3-code-review.md)
- [4. Fetching the Latest](4-fetching-latest.md)
- [5. Hotfix](5-hotfix.md)
- [6. Release Branch](6-release-branch.md)
- [7. Release Bugs](7-release-bugs.md)
- [8. Completed Release](8-completed-release.md)
