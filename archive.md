---
layout: page
title: Blog Archive
---

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
{% for year in posts_by_year %}
<div class="archive-group">
  <h3>{{ year.name }}</h3>
  <ul>
    {% for post in year.items %}
    <li>
      <span class="archive-date">{{ post.date | date: "%b %-d" }}</span>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
</div>
{% endfor %}

{% if site.posts.size == 0 %}
<p class="empty-note">No posts yet.</p>
{% endif %}
