---
layout: archive
permalink: /posts/
title: "Posts"
author_profile: true
header:
  image: "/images/header_logo_01.jpg"
---

{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in site.posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}