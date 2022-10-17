---
title:
- Free Software and Version Control 101
subtitle:
- A introductory course on FOSS, git, curl and web integrations
author:
- J. Rodrigues
- F. Carvalho
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

# Tools

## git?

Git is a version control software created by Linus Torvalds (which also created the Linux Kernel).
Its free software under the GPL v2.0.

Git allows cloning, pulling, pushing, etc. of data stored in git instances.

## curl?

Curl (short for client-url), is the command line tool that makes use of libcurl,
a data transfer library that supports a array of network protocols such as FTP, HTTP, etc.

We will use curl to communicate with the GitHub API in the next sections.

Curl and libcurl are FOSS licensed under the curl license, based on the MIT License, and compatible with the GPL v3.0

# How does git instance work?

## Repositories and actions
![Actions and interactions between repositories](./git-transport.png){height=260px}

## A pratical example: hackerschool.io
![Git/GitHub flow of the hackerschool.io repository](./git-transportHS.png){height=260px}

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
Let's start with creating a remote and local repository

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

## Add

## Commit

## Push

# Working together!

## Cloning

## Pulling

## Forking with the web

## Merging with the web

## Other Actions!

# Tying our work with freedom

## On FOSS and CC

The first written document that described FOSS as a trend among hackers, programmers, engineers, etc. was the GNU Manifesto. This file also gave the philosophical foundations for the Free Software Foundation Network, and FOSS worldwide.

In the context of HackerSchool FOSS is a core principle. Initiated in the administration of 22-23, HackerSchool has embraced free alternatives such as _GNU/Linux distros, FreeCAD, Jitsi, Signal_, allowing hackers to walk a path that is flexible, secure, and overall hacker-y.

Since we benefit from this communal effort it is only fair that we also contribute to the greater good, therefore all HackerSchool code and documents are non-proprietary.

## The two software architectures

+ **The Cathedral**

	We can apply this architectural decision to both:

	+ **Free Software**

		The source code is centralized in an organizational environment, however it is released with any main binary. You will rarely look to the code in development.

	+ **Proprietary Software**

		The source code is never released, it is kept confined within the Corporations walls. The binary is spewed out of it, but you will have to reverse it to understand what it does! 

## The two software architectures
+ **The Bazaar**

	The Bazaar is characteristic of free software.

	In a Bazaar architecture the source code is visible at all times, being normally communal projects, made of differently written modules. Its all nodes that compose a de-centralized tree! 

	This architecture as the advantage of going according to Linus's Law:


	_"given enough eyeballs, all bugs are shallow"_

## Licenses

![Licenses and properties](./table.png){height=260px}


