---
layout: page
title: talks
permalink: /talks/
nav: true
nav_order: 3
---

{% for talk in site.talks reversed %}
  <h3>{{ talk.title }}</h3>
  <p>{{ talk.date | date: "%B %Y" }} · {{ talk.venue }}</p>
  {{ talk.content }}
{% endfor %}