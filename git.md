# Git

![git](https://git-scm.com/images/logos/2color-lightbg@2x.png)

## Configuring Your Name & Email

`git config --global user.name "Your Name"`  
`git config --global user.email "your@email.com"`

## Initializing a local repository

Create a new repository either locally then push to GitHub or by cloning an existing repository.  
`git init`  
Turn an existing directory into a git repository

example

```cmd
C:\users\frago\documents\dev\SupportDirectory> git init
Initialized empty Git repository in C:/Users/frago/Documents/dev/SupportDirectory/.git/
```

## Local Changes

`git status`  
Show unstaged changes

example

```cmd
C:\users\frago\documents\pyscripts\dev\SupportDirectory> git status
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
        new file:   supdir.cs
```

## Stage

`git add [file]`  
Snapshots a single file in preparation for versioning

`git add file1.cs file2.cs file3.cs`  
Adds multiple files

`git add .`  
Stage all changed files, ready for commit

example

```cmd
C:\users\frago\documents\dev\SupportDirectory> git add supdir.cs
```

This command returns void

## Commit Local Repository

```cmd
git commit -m "[descriptive message]"
Records file snapshots permanently in version history

C:\users\frago\documents\dev\SupportDirectory> git commit -m "This is a git-commit"
[master 506838f] This is a git-commit
1 file changed, 1 insertion(+)
create mode 100644 supdir.cs
```

Use `git log` to check history of your commits  
Use `git checkout <commit hash>` to revert between commits in a deteached HEAD state (More on `git checkout` in the Branches section)

## Remote repository

### Local >> Remote  

Turn an existing directory into a Git repository and push to remote repo

```cmd
git remote add origin [existing repo url]
git push -u origin master
```

### Remote >> Local

```cmd
 git clone [url]
Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits
```

`git clone https://username@github.com/username/repo_name.git`

```cmd
git clone https://panchi81@github.com/panchi81/pypt.git
```

```cmd
echo "# NLP_with_Python" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/Canelabiz/NLP_with_Python.git
git push -u origin master
```

### Branches

Branches are an important part of working with Git. Enabling a parallel "timeline" of your project.  
Any commits you make will be made on the branch you're currently "checked out" to.  
Use `git status` to see which branch that is.

`git branch`  
Lists branches

`git branch <new branch-name>`  
Creates a new branch

`git branch -d [branch-name]`  
Deletes the specified branch

`git checkout [branch-name]`  
Switches to the specified branch and updates the working directory

`git checkout -b [new branch name]`  
Create a new branch and switch to it

`git merge [branch]`  
Combines the specified branch´s. This is usually done in pull requests, but is an important Git operation

## Synchronize

`git fetch [remote] [branch]`  
Get changes without merging

`git pull`  
Get (pull) changes and merge

`git push`  
Upload (push) changes

`git push -u origin [branch]`  
Upload new branch to origin remote

`git command --help`  
use git help

```sequence
Title: Git
Working Directory->Stage: git add
Stage->Local Repository: git commit
Working Directory->Local Repository: git commit -a
Local Repository->Remote Repository: git push
Remote Repository->Local Repository: git fetch
Local Repository->Working Directory: git merge
Remote Repository->Working Directory: git pull
```

### The .gitgnore file

Sometimes it may be a good idea to exclude files from being
tracked with Git. This is typically done in a special file named
`.gitignore`. You can find helpful templates for `.gitignore`
files at [github.com/github/gitignore](github.com/github/gitignore)

Links:

* [Git](https://git-scm.com/)
* [GitHub Git Cheat Sheet - GitHub Cheatsheets](https://github.github.com/training-kit/downloads/github-git-cheat-sheet/)
* [Git - Book](https://git-scm.com/book)
* [An Intro to Git and GitHub for Beginners (Tutorial)](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)
* [TF400813: Resource not available for anonymous access. Client authentication required. - Microsoft Team Foundation Server](https://tfs.beijerelectronics.com/HmiDev/TFS-TestProject/_versionControl)
* [Git Basics Simply Explained For Beginners](https://blog.shahednasser.com/git-basics-for-beginners/)
