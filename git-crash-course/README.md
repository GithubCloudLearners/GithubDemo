## Git Hiddern Folder
There is a hidder folder called `.git` which tells your that our project is a get repo.

If we wanted to created a git repo is a new project we create the folder and initialize that repo using `git init`
```sh
mkdir /workspaces/tmp/new-project
cd /worspaces/tmp/new-project
git init
touch Readme.md
code Readne.md
git status
git add . #Make changes to all files
git add Readme.md #Make changes to Readme.md only
git commit -a -m "Add readme files"
```

## Clone
You can use HTTPS, SSH or GitHub CLI
### HTTPS
```sh
mkdir tmp
cd /workspaces/tmp
```

```sh
git clone https://github.com/AndresMPaws/GithubDemo.git
cd GithubDemo
```

## Commits
When we want to commit code we can write git commit which will open up the commit edit message in editor of choice. 
Make commit and commit messages without opening an editor
```sh 
git commmit -m "Message
```
Set global editor
```sh 
git config --global core.editor emacs
```
## Branchs

## Remotes

## Stashing

## Merging

## Add
When we want to staged changes that will be included in the commit
We can staged all with ```add .```
We can staged a specific file with ```add Readme.md```


## Reset 
Reset allows you to move Staged changes to be unstaged.
This is a useful when you to revert all files not to be commited.

```sh
git add .
git reset
```
>git reset will revert a git add

## Status
Git status shows you what files will or not be commited

```sh
git status
```

## Gitconfig file
The gitconfig file is what stores your global configurations for git such an email, name, editor and more

Showing the contents of our .gitconfig file
```
git config --list
```

When you first install Git on a machine you are suppose to set up your name and email.
```sh
git config --config user.name "AndresMP"
git config --config user.email "andresmunozpampillon@gmail.com"
```