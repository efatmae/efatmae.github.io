---
layout: single
title: "Struggles"
permalink: /struggles/
author_profile: true
---
{% if author.googlescholar %} You can also find my articles on my Google Scholar profile. {% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
{% include archive-single.html %}
{% endfor %}

