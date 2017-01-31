---
layout: post
title: "Setting up Git on Synology Diskstation"
description: ""
category: 
tags: [git,synology]
---
{% include JB/setup %}

Installed Git on my Synology Diskstation (Play214), created a repo for personal game project, and did my first git add/git commit/git push!
I followed this helpful guide found here -> http://blog.netgloo.com/2015/04/20/git-server-on-synology-ds115j-installation-and-configurations/

Steps:
-- Install Git Server package on Diskstation
-- Create new user named "gituser"
-- Add a new shared folder called "git", give read/write access to "gituser" and "admin"
-- Open Git Server and give "gituser" permissions
-- Enable SSH access on Diskstation (Control Panel -> Terminal & SNMP -> Enable SSH Service)

For the next steps I used PuTTY since I'm on Windows, but you can use Terminal instead if you're on Linux.
-- Add shared repository 
$ ssh <adminuser>@diskstation -p <port>
$ cd /volume1/git
$ git init --bare --shared <projectname>.git

I installed Git for Windows (https://git-scm.com/downloads)
-- since I had a project already on my local pc, I just had to do the following
-- Open Git CMD (alternatively you could use GIT Bash, which I realized after the fact)
> cd <path to project>
> git init
> git remote add origin ssh://gituser@diskstation:<port>/volume1/git/<projectname>.git
> git add --all
> git commit -a -m "Initial commit"
> git push -u origin master

It then asks for the password, and pushes the changes to the Git Server. Now I have a local Git Server to store my personal projects!

Next thing I want to do is use public key authentication.