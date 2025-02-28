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
      <img src="{{ member.picture }}" alt="{{ member.name }}'s Profile Picture" class="profile-image">
      <div class="member-info">
        <h2>{{ member.name }}</h2>
        <p><strong>Role:</strong> {{ member.role }}</p>
        <p><strong>Summary:</strong> {{ member.summary }}</p>
      </div>
    </li>
  {% endfor %}
</ul>