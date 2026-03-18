---
permalink: /blog/
title: "Writing"
layout: single
author_profile: false
---

<div style="max-width: 680px;">

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year_group in posts_by_year %}
  <div class="blog-year-group">
    <h3 class="blog-year-label">{{ year_group.name }}</h3>
    {% for post in year_group.items %}
      <div class="blog-post-row">
        <span class="blog-post-row__title">
          <a href="{{ post.url }}">{{ post.title }}</a>
        </span>
        <span class="blog-post-row__date">{{ post.date | date: "%b %d" }}</span>
      </div>
    {% endfor %}
  </div>
{% endfor %}

{% if site.posts.size == 0 %}
  <p style="color: var(--color-text-muted); font-size: 0.9375em;">Posts coming soon.</p>
{% endif %}

</div>
