---
layout: page
title: Hello Yang!
tagline: SilentLake 
---
{% include JB/setup %}



Get more

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

