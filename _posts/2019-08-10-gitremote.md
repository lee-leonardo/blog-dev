---
layout: post
title: "Git Remotes and the Beauty of Forking"
categories: [blog, coding, git, github]
tags: [ghost, blogging]
---

# Introductions

This post requires some prerequisite knowledge in the basics of git.
I'll do my best to explain terms as I go, but I'll look to developing another post that will give an overview and sources to get people up to speed.
TBH there is not easy way to learn the basics of git without pragmatic practice.
I will try to make this blog post systematic as possible to facilitate the learning of both myself and others.

## Terms

### Repository

The place where the code resides.
A repository consists of a folder that is used by git (`/.git/`) to manage the code that is within the parent folder of this hidden folder.
The means of which is performed by a command line interface tool that piggybacks off Linus Torvald's work on the UNIX operating system.
The most notable piece of software in git is the nice wrapper around UNIX's _diff_, this program compares two files, by line, and marcates the lines that are different.
The other major component of git is the ledger that record snapshots of changes, a timeline of sorts, called the commit history. It is a written record of what code has been preserved in git.

### Fork

A copy of a repository, usually set up so that it can communicate with the original repository. This copy has it's own copy of everything, it can resolve it's history against the master branch.

### Remote

Remote describes a copy of the repository that is not local. e.g. it is somewhere in the internet or on another computer.
A good analogy is that remote branches are timeline, from which your local copy will ultimately diverge from.

### Branch

A signifier of where the commit history is being modified from.
Think of it like the position in time from where the timeline diverges from.
Within a branch there is a pointer (think pin on the timeline) that is called HEAD. This usually is the latest commit in the commit history.

### master

Describes the branch that is considered to be the source of truth for the repository. It is best practice to not directly modify it, rather use the merging functionality of git to make edits to this branch.

### origin

Where the code was copied from. This can be where the code originally is from, but not guaranteed. For example if you fork a copy of a project, and then clone that repository locally, that fork would be origin.

### upstream

Typically used to describe the communications between your local copy of the repository and the origin repository.
Essentially it's a term to send copied of branches from local to origin, and the comparision of the state of the branch between what is in origin and local.

## How to add a remote repository

Adding a remote repository is done by the set of commands located in the command `git remote` (see a list of these commands with the command `git remote -h`).

### 01. Get the url to the remote repository

This step is pretty straightforward, what you essentially need to do is to go to the internet location of the repository and find the url to copy either via SSH or HTML (SVG's url is the same as the HTML).

### 02. Add a remote repository

- Forumla: `git remote add <remote name (local)> <repository url>`
    - Example (SSH): `git remote add ghost git@github.com:TryGhost/Ghost.git`
    - Example (HTML): `git remote add ghost https://github.com/TryGhost/Ghost.git`

### 03. Verify the remote link was created

- Formula: `git remote -v` or `git remote --verbose`

### 04. How to use the remote

- Forumla (Pulling from master): `git remote pull <remote name> <branch name>`
    - Example: `git remote pull ghost feature_1`
- Forumla (Pushin to a branch): `git remote push <remote name> <branch name>`
    - Example: `git remote pull ghost feature_1`

If the remote repository is not specified it works against origin.
If a branch name isn't specified it works against the checked out one.
The commit history of the branches can be different, so if you may need to push to both to keep multiple branches in sync.
