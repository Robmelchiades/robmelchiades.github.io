---
layout: archive
permalink: /posts/
title: "Posts"
author_profile: true
header:
  image: "/images/header_logo_01.jpg"
---

<!-- {% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in site.posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %} -->

<!-- {% for post in site.cienciadacomputacao %}
  {% include archive-single.html %}
{% endfor %} -->

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h2 id="{{ year | slugify }}" class="archive__subtitle">{{ year }}</h2>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}