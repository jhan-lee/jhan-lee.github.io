---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

{% for category in site.cv_category %}
  {% assign title_shown = false %}
  {% for post in site.publications reversed %}
    {% if post.cv_category != category[0] %}
      {% continue %}
    {% endif %}
    {% unless title_shown %}
<h2>{{ category[1].title }}</h2>
<ul>
      {% assign title_shown = true %}
    {% endunless %}
    {% include archive-single-cv.html %}
  {% endfor %}
  {% for post in site.portfolio %}
    {% if post.cv_category != category[0] %}
      {% continue %}
    {% endif %}
    {% unless title_shown %}
<h2>{{ category[1].title }}</h2>
<ul>
      {% assign title_shown = true %}
    {% endunless %}
    {% include archive-single-cv.html %}
  {% endfor %}
  {% for post in site.teaching %}
    {% if post.cv_category != category[0] %}
      {% continue %}
    {% endif %}
    {% unless title_shown %}
<h2>{{ category[1].title }}</h2>
<ul>
      {% assign title_shown = true %}
    {% endunless %}
    {% include archive-single-cv.html %}
  {% endfor %}
  {% if title_shown %}
</ul>
  {% endif %}
{% endfor %}
