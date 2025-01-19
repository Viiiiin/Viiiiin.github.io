---
layout: page
title: Statistics
subtitle: My homework for statistics
---

<div class="presentation">
  <section class="intro">
    <h1>Welcome to my Blog</h1>
    <p>Discover insightful articles, updates, and more. Stay informed and inspired with our curated content.</p>
  </section>

  <section class="featured-posts">
    <h2>Featured Posts</h2>
    <ul class="posts-list list-unstyled" role="list">
      {% assign posts = paginator.posts | default: site.posts %}
      {% for post in posts limit: 11 %}
      <li class="post-preview">
        <article>

          {% if post.thumbnail-img %}
          <div class="post-image">
            <a href="{{ post.url | absolute_url }}" aria-label="Thumbnail">
              <img src="{{ post.thumbnail-img | absolute_url }}" alt="{{ post.title }} thumbnail">
            </a>
          </div>
          {% endif %}

          <a href="{{ post.url | absolute_url }}">
            <h3 class="post-title">{{ post.title | strip_html }}</h3>
          </a>

          {% if post.subtitle %}
          <p class="post-subtitle">{{ post.subtitle | strip_html }}</p>
          {% endif %}

          <p class="post-meta">
            {% assign date_format = site.date_format | default: "%B %-d, %Y" %}
            Posted on {{ post.date | date: date_format }}
          </p>

          <div class="post-excerpt">
            {{ post.excerpt | strip_html | truncatewords: 30 }}
            <a href="{{ post.url | absolute_url }}" class="post-read-more">Read more</a>
          </div>

        </article>
      </li>
      {% endfor %}
    </ul>
  </section>

