---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
hide_title: true
redirect_from:
  - /resume
---

{% include base_path %}

{% for category in site.cv_category %}
<h1>{{ category[1].title }}</h1>
<ul>
  {% for post in site.publications reversed %}
    {% if post.cv_category == category[0] %}
      {% include archive-single-cv.html %}
    {% endif %}
  {% endfor %}
  {% for post in site.portfolio %}
    {% if post.cv_category == category[0] %}
      {% include archive-single-cv.html %}
    {% endif %}
  {% endfor %}
  {% for post in site.teaching %}
    {% if post.cv_category == category[0] %}
      {% include archive-single-cv.html %}
    {% endif %}
  {% endfor %}
</ul>
{% endfor %}
