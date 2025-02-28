---
layout: page
title: Alumni
subtitle: These are the alumni of the project
permalink: /alumni/
image: ../assets/images/gallery/members3.jpg

---

<ul class="alumni-list">
  {% for alumni in site.data.alumni %}
    <li class="alumni">
      <img src="{{ alumni.picture }}" alt="{{ alumni.name }}'s Profile Picture" class="profile-image">
      <div class="alumni-info">
        <h2>{{ alumni.name }}</h2>
        <p><strong>Role:</strong> {{ alumni.role }}</p>
        <p><strong>Summary:</strong> {{ alumni.summary }}</p>
      </div>
    </li>
  {% endfor %}
</ul>