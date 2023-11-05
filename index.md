---
layout: default
title: Home
---

Hello, world! This blog will be a forum for me to explore topics that can be addressed with data, assisted by code. 
It is as an opportunity to learn about interesting substantive topics about how the world works, beginning with the energy market in the U.S. 
Conversations always welcome. 

{% for post in site.posts %}
### <a href="{{ post.url }}">{{ post.title }}</a>
{{ post.date | date: "%-d %B %Y" }}
{{ post.excerpt }}
<a href="{{ post.url }}">(more...)</a>
{% endfor %}

