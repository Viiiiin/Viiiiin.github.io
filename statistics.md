---
layout: page
title: Statistics
subtitle: My homework for statistics
---

My statistics homework

### HomeWorks

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}
