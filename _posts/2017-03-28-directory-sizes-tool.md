---
layout: post
title: "Directory Sizes Tool"
date: 2017-03-27
tags: [C#, .Net, Windows, Tools]
---
{% include JB/setup %}

One of the things I always disliked doing was finding that I was running out of space on a disk, and manually search for directories/files that were really large so I could delete them and clear up space.

While you can easily identify Program sizes through Add/Remove Programs in Windows Control Panel, it isn't as easy to find folders that contain miscellaneous files like music, pictures, movies, etc. I looked for a tool that could give the the sizes of each directory (total, summed up from subdirectories), but could not find one.

So, I created one!

[Directory Sizes Tool](https://github.com/r-abbott/DirectorySizesTool) is a simple tool that scans a drive, compiles all the directory sizes, and displays them in a format that helps you quickly see the large ones.

<h3>Quick Walkthrough</h3>

When first running the application, it will ask for a drive.

<img style="width: 820px;" src="https://github.com/r-abbott/DirectorySizesTool/blob/master/screenshots/FirstOpen.png?raw=true" title="first run view"/>

It will read the drive, save the compiled data to disk, and display the root directory with a list of subdirectories and their sizes.

<img style="width: 820px;" src="https://github.com/r-abbott/DirectorySizesTool/blob/master/screenshots/InitialRead.png?raw=true" title="root directory view"/>

- You can also navigate to subdirectories:

<img style="width: 820px;" src="https://github.com/r-abbott/DirectorySizesTool/blob/master/screenshots/cd.png?raw=true" title="cd example"/>

- discover large directories:

<img style="width: 820px;" src="https://github.com/r-abbott/DirectorySizesTool/blob/master/screenshots/discover.png?raw=true" title="discover example"/>

- find directories that are greater than a size:

<img style="width: 820px;" src="https://github.com/r-abbott/DirectorySizesTool/blob/master/screenshots/greater.png?raw=true" title="greater example"/>

- and open the directories in Windows Explorer:

<img style="width: 820px;" src="https://github.com/r-abbott/DirectorySizesTool/blob/master/screenshots/open.png?raw=true" title="open example"/>

I've personally used the tool to find huge picture directories, random phone backup directories, and even some games I had forgotten about.

If you find this tool useful, let me know. And if you would like to collaborate on it, send me a pull request.