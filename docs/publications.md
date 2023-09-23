---
layout: page
title: Publications
subtitle: Papers published from our research activities
permalink: /publications/
image: /images/smart-ag.jpeg
---

<ul>
{% for publication in site.data.publications %}
  <li>{{ publication.citation }}</li>
{% endfor %}
</ul>