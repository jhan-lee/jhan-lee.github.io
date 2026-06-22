---
layout: archive
title: "Other Activities"
permalink: /other-activities/
author_profile: true
hide_title: true
redirect_from:
  - /cv/
  - /resume
---

{% include base_path %}

{% for category in site.cv_category %}
<h1>{{ category[1].title }}</h1>
{% if category[0] == 'achievements' %}
<div class="achievements">
  {% for post in site.achievements reversed %}
    {% include achievement-entry.html post=post %}
  {% endfor %}
</div>
{% else %}
<ul>
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
{% endif %}
{% endfor %}
