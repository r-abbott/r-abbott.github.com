---
layout: post
title: "Get Package"
date: 2017-02-02 05:45 UTC
tags: [NuGet,Nuget Package Manager Console]
---
{% include JB/setup %}

I had to get a list of all 3rd party packages for a security audit. After a quick Google of how to export the Solution packages, I found in the NuGet Package Manager Console there is a command:

```
Get-Package
```

Which lists all of the Packages, nicely formatted with Id, Version, and Description/Release Notes.

Saved me the trouble of having to write something to parse all the packages myself.

I also wrote a little application that goes through a project and gets all the javascript files, and tries to do something similar to what Get-Package does.

I had it grab the file name, directory, and parse out the header description if it existed. Which, if you've ever looked at 3rd party javascript files, is not always easy to do. I settled on looking for some sort of comment block and grabbing the text there, as well as including the directory and file name. After a quick manual check I could get an idea of what most of the libraries were.
