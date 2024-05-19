---
title: "Python"
layout: category
permalink: /categories/python/
author_profile: true
taxonomy: Python
sidebar:
  nav: "categories"
---

{% assign posts = site.categories.Python %}
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} {% endfor %}
