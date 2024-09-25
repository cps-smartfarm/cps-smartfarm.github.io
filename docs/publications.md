---
layout: page
title: Publications
subtitle: Papers published from our research activities
permalink: /publications/
image: /images/smart-ag.jpeg
---
{% assign publications_by_year = site.data.publications | group_by: 'year' %}

<ul>
{% for year_group in publications_by_year %}
  <li>{{ year_group.name }}</li>
  <ul>
    {% for publication in year_group.items %}
      <li class="publication">{{ publication.citation }}</li>
    {% endfor %}
  </ul>
{% endfor %}
</ul>
