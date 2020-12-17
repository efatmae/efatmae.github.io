---
layout: single
title: "Struggles"
permalink: /struggles/
author_profile: true
---
{% include base_path %}

{% for post in site.struggles reversed %}
{% include archive-single.html %}
{% endfor %}

