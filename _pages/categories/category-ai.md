---
title: "AI"
layout: category
permalink: /categories/ai/
author_profile: true
taxonomy: AI
sidebar:
  nav: "categories"
---

{% assign posts = site.categories.AI %}
{% for post in posts %} {% include archive-single2.html type=page.entries_layout %} {% endfor %}