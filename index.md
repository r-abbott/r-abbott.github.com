---
layout: page
title: Ryan's Blog
tagline: Adventures in Software
---
{% include JB/setup %}

{% for post in paginator.posts %}

   <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
   <div class="date">{{post.date | date: "%A, %d %B %Y %H:%M:%S %Z" }}</div>
   <div>
    {{ post.content }}
   </div>
   <hr>
{% endfor %}

