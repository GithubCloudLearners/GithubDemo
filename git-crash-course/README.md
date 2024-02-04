# **GIT w/GITHUB BASICS**

## Git Hidden Folder
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

### SSH


```sh
git clone git@github.com:AndresMPaws/GithubDemo.git
cd GithubDemo
```

We will have to create our SSH rsa key pair
```sh
ssh-keygen -t rsa
```
And copy and paste de public key in github, getting it from
```sh
cat /your_directory/.ssh/id_rsa.pub
```
For test our connection run
```sh
ssh -T git@github.com
```
### CLI
For installing on windows
```sh
gh repo clone AndresMPaws/GithubDemo
winget upgrade --id GitHub.cli
```

We have to login using the CLI and clone the repo
```sh
gh auth login
gh repo clone AndresMPaws/GithubDemo    
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
List of branchs
```sh
git branch
```

Create new branch (dev)
```sh
git branch branch-name
```

Checkout the branch (dev)
```sh
git checkout branch-name
```

## Remotes
We can add remotes but often you will add remotes via upstream when adding a branch
```sh
git remote add ...
git branch -u origin new-features
```
## Stashing
If we want to save a work in progress by add but without commiting it into the branch. We can "save" it by stashing. So we can bring it back by poping it

```sh
git add .
git stash #"Save" our work in progress
git stash pop #Bring it our work in progress back
```
The stash work in progress wi be put into a list of changes. 
```sh
git stash list
```

Another option is name our stash and bring back the last one
```sh
git add .
git stash save name-of-stash
git stash apply
```


## Merging
If we want to integrate the work (merge) developed in the branch dev into the main branch we do.

```sh
git checkout main
git merge dev
```

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

## Log
Show recent git commits to the git tree
```
git log
```

## Push
Push a repo to the remote origin
```
git push
```


# **SOME GITHUB CLI BASICS**

## Token
We can check the default token of our codespace
```sh
gh auth token
```

But we can set a new token with especific permisions and expire date by

```sh
export GH_TOKEN="your_token"
env | grep GH #Should return the token generated value
gh auth token #Now must be change and return the token generated value
```

## Set defaul repo
We can set our default repo by
```sh
gh repo set-default
```

## Checks issues
```sh
gh issue list
```

## Create an issue
We can create a new issue by:
```sh
gh issue create --title "I found a bug" --body "Something do not work"
```

## Delete an issue
We can delete an issue with it´s number id:
```sh
gh issue delete number_of_issue
```