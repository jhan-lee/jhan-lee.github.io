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
<ul class="cv-list">
  {% for post in site.achievements reversed %}
    {% include achievement-entry.html post=post %}
  {% endfor %}
</ul>
{% else %}
<ul class="cv-list">
  {% for post in site.activities reversed %}
    {% if post.cv_category == category[0] %}
      {% include activity-entry.html post=post %}
    {% endif %}
  {% endfor %}
</ul>
{% endif %}
{% endfor %}
