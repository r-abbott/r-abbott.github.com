---
layout: post
title: "TDD Spy Decryptor"
date: 2017-03-02 18:00:00 UTC
tags: [Test Driven Development, Encryption, Tutorial, C#]
---
{% include JB/setup %}

I have been looking around for some good tutorials or small project walkthroughs to do Test Driven Development with, and most of them have to do with creating a coffee machine. A few that I read through don't have you working with a UI or another external service or app, so there's no real feeling of progressing and having some end goal in mind (albeit learning/getting better at TDD is the real end goal, I prefer to see some visual progress.)

Many of the projects I have looked at say things like (let's use coffee machine as an example)
- You don't have to write the interface that the user interacts with
- You don't have to write the dispenser/brewer/grinder/coffee-master-9000 device
- You just write the "logic" in between the user interface and the dispenser.

Ok, so from the get go I feel a little put-off because:
1. I know I'm going to either have to Mock an interface or create a Fake, so yes I'm in fact going to have to create these.
2. I won't really get to play with the thing I'm creating.

So, I thought I would create my own little TDD project. No, as much as I do enjoy coffee it is not yet-another-coffee-machine project. It's a Spy (!) project, where you are tasked with decrypting intercepted messages. While you are writing the decryptors using TDD, the end goal is to decrypt an entire intercepted message. And it comes with that process already (an "Uplink" class that you put your decryptor into), so you don't have write any Mocks or Fakes in order to check out the whole thing.

[Check it out](https://github.com/r-abbott/SpyTDD), and let me know what you think!