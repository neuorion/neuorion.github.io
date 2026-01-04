---
layout: default  # Or your main layout
title: Blog
permalink: /blog/
---

<h1>Latest Blog Posts</h1>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> 
      <small>{{ post.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>