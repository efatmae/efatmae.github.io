---
layout: single
title: "Women in NLP"
permalink: /womenInNlp/
author_profile: true
---
{% include base_path %}
Women in NLP is an initiative to support and encourage women to work on natural language processing (NLP) problems. We hold monthly talks where we invite women who successfully carved their career path in NLP to share their experiences and advice. Everyone is welcome to the talks not only women.
The events are announced on MeetUp and announced on my Twitter account @fatmaElsafoury.
To suggest a guest please contact me on e.fatma.e@gmail.com

We also organize online meetings where women come together to support one another.
To know about these meetings please join the #Women_in_NLP channel on Slack <a href="https://dairai.slack.com/archives/C01J0GXJMD1">channel on Slack</a>.

{% for post in site.womenInNlp reversed %}
{% include archive-single.html %}
{% endfor %}
