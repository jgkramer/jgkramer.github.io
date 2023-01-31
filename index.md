---
layout: default
title: Turkeys in the Desert
---

Hello, world! This blog will be a forum for me to explore topics that can be addressed with data, assisted by code. 
I think of it as an opportunity to learn about interesting substantive topics about how the world works (starting with the energy market in the U.S.), 
as well as develop my programming and visualization skills.


{% for post in site.posts %}
### <a href="{{ post.url }}">{{ post.title }}</a>
{{ post.date | date: "%-d %B %Y" }}
{{ post.excerpt }}
<a href="{{ post.url }}">(more...)</a>
{% endfor %}

