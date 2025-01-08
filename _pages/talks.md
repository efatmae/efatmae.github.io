---
layout: archive
title: "Talks"
permalink: /talks/
author_profile: true
---
{% if author.googlescholar %} You can also find my articles on my Google Scholar profile. {% endif %}

{% include base_path %}

{% for post in site.talks reversed %}
{% include archive-single.html %}
{% endfor %}

