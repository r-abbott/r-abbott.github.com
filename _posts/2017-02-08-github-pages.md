---
layout: post
title: "Github Pages"
date: 2017-02-08 18:00:00 UTC
tags: [GitHub,Jekyll,Blog]
---
{% include JB/setup %}

Set up my first Github page using Jekyll Bootstrap. It took a little bit of work to get the page working how I wanted (I still can't get the code highlighting to work properly), but all in all a good start.

I currently have the index displaying the 10 most recent posts. I liked the way [@ploeh](http://blog.ploeh.dk) did his, so I took a peek and found he was using jekyll pagination.

I found out I had to add the gem to the _config.yaml:

### _config.yaml
{% highlight bash%}
gems: ["jekyll-sitemap", "jekyll-paginate"]
{% endhighlight %}

And then create index.html (and remove index.md):

### index.html

{% highlight html%}
{% raw %}{% for post in paginator.posts %}{% endraw %}
   <h2><a href="{% raw %}{{ post.url }}{% endraw %}">{% raw %}{{ post.title }}{% endraw %}</a></h2>
   <div class="date">{% raw %}{{post.date | date: "%A, %d %B %Y %H:%M:%S %Z" }}{% endraw %}</div>
   <div>
    {% raw %}{{ post.content }}{% endraw %}
   </div>
   <hr>
{% raw %}{% endfor %}{% endraw %}

<!-- Pagination links -->
<div class="pagination">
{% raw %}{% if paginator.previous_page %}{% endraw %}
    <a href="/page{% raw %}{{paginator.previous_page}}{% endraw %}" class="next">Next</a>
{% raw %}{% else %}
  {% endif %}
  {% if paginator.next_page %}{% endraw %}
    <a href="/page{% raw %}{{paginator.next_page}}{% endraw %}" class="previous ">Previous</a>
{% raw %}{% else %}
  {% endif %}{% endraw %}
</div>
<div class="page_number ">Page {% raw %}{{paginator.page}}{% endraw %} of {% raw %}{{paginator.total_pages}}{% endraw %}</div>
{% endhighlight %}

Which nicely lists out the posts along with date and content.

I realize if you are reading this on my GitHub page, this may be kind of a Terminator time-travel paradox as this isn't the first post on here.
