---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

_Please feel free to contact me if you'd like a PDF of any of these articles! I'd be happy to share._
{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
