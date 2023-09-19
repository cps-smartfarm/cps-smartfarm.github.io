---
layout: page
title: Publications
subtitle: Paper published from our project
permalink: /publications/
---

<ul>
{% for publication in site.data.publications %}
  <li>{{ publication.citation }}</li>
{% endfor %}
</ul>