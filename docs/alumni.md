---
layout: page
title: Alumni
subtitle: These are the alumni of the project
permalink: /alumni/
image: ../assets/images/gallery/members3.jpg

---

<ul class="members-list">
  {% for member in site.data.members %}
    <li class="member">
      <img src="{{ alumni.picture }}" alt="{{ alumni.name }}'s Profile Picture" class="profile-image">
      <div class="member-info">
        <h2>{{ alumni.name }}</h2>
        <p><strong>Role:</strong> {{ alumni.role }}</p>
        <p><strong>Summary:</strong> {{ alumni.summary }}</p>
      </div>
    </li>
  {% endfor %}
</ul>