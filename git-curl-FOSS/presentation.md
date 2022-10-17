---
title:
- Free Software and Version Control 101
subtitle:
- A introductory course on FOSS, git, curl and web integrations
author:
- João Barreiros C. Rodrigues
- Francisco Carvalho
- Nuno Abreu
institute:
- HackerSchool
fonttheme:
- "professionalfonts"
monofont:
- "Source Code"
theme:
- CambridgeUS
colortheme:
- beaver
---

# Version control?

## What is version control?

Version control is the practice of managing and documenting _data_ (code, schematics, etc.)
iterations.

It is particularly important in our context of Free and Open Source software,
as a careful documentation of alterations between versions and the ability to inspect
older or deprecated sources can make issue resolution and feature integration much more agile.

### git?

Git is a version control software created by Linus Torvalds (which also created the Linux Kernel).
Its free software under the GPL v2.0.

Git allows cloning, pulling, pushing, etc. of data stored in git instances.

##  
It has happened to all of us!
![Development without SCM](./noGit.png)
Time to ditch this...

## For something waaaay better
![git log](./gitLog.png)

##

![](./gitDiff.png)

## curl?

Curl (short for client-url), is the command line tool that makes use of libcurl,
a data transfer library that supports a array of network protocols such as FTP, HTTP, etc.

We will use curl to communicate with the GitHub API in the next sections.

Curl and libcurl are FOSS licensed under the curl license, based on the MIT License, and compatible with the GPL v3.0

# Let's Start!

## Setting up your git/GitHub environment
+ Create a GitHub account (using your institutional e-mail is often valuable).
+ Get the git and curl packages.
+ Generate a OAuth key, ssh key, or any mean of remote authentication.
+ Save it somewhere safe (encrypt it with gpg, or use a password manager (for example: keepass).

Let's waddle back to the terminal

```bash
git config --global user.name "@user.name" 

git config --global user.email @user.email
```

## Setting up a GitHub repository with curl and git
Let's start with creating a remote and local repository (note: this can also be done in github's website)

```bash
curl -u @user https://api.github.com/user/repos -d \
'{"name":"@string","private":false}' 

mkdir @string && cd @string
```
Now we can initialize our local repo and link it to the remote one

```bash
git init

git remote add origin https://github.com/@name/@string.git

```

# Your first commit!

## Git Status
This command alows you to view the state of your project (repo)
![Git Status](./gitStatus.png)


## Add
- When we want the git log changes made to a file `git add <file_path>` 
- When the file hasn't ever been tracked `add` tells git to start to
- This command only selects the files/modifications, it **does not** commit 

![Git Add](./gitAdd.png)


## Commit
- To commit (record the selected changes to the history) we use the command `git commit -m "commit message"`

![git commit](./gitCommit.png)

## Push
- You can push your history to a remote repo using the command `git push <name_of_remote_repo>`
    - Usually when using Github this remote is called **origin**
- You can even have multiple remotes!
    - to add one use `git remote add <name> <url>`, as seen in the curl part of this presentation

![git push](./gitPush.png)

## Frontends (Vscode)


# Working together!

### Cloning
Cloning allows you to download a git remote repository
```bash
git clone https://github.com/HackerSchool/inar.git
```

### Pulling
Oposite of push, allows you to download remote changes to your existing local repo
```bash
git pull origin
```

## Forking
Note: This is a feature of Github and not git itself

- Forking is an important collaboration tool as it allows you to make your own private copy of an exciting repository
- This means you can work freely, without pushing "trash" to the main repo
    - You can even start your own version of the project!
- Once you're ready to merge your changes into the main repo you can open a **pull request**
    - This is one way of contributing code to a public repo if you aren't a contributor (=have write access)
- In medium-small projects, branching may be enough

![](./forkBtn.png)

## Pull Requests
![](./forking2.png)

When we want to merge with the original repo we open a pull request
![](./PR.png)


# Tying our work with freedom

## On FOSS

## Licenses