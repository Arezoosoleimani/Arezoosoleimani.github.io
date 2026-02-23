---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

<h2>Books</h2>
{% assign books = site.publications | where: "pubtype", "book" | sort: "date" | reverse %}
{% for post in books %}
  {% include archive-single.html %}
{% endfor %}

<h2>Papers</h2>
{% assign papers = site.publications | where_exp: "item", "item.pubtype != 'book'" | sort: "date" | reverse %}
{% for post in papers %}
  {% include archive-single.html %}
{% endfor %}
