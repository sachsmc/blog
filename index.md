---
layout: page
title: Hello World!
tagline: Getting Set up
---
{% include JB/setup %}

## First post coming soon
Title: Creating Interactive Brownian Bridges using d3.js

## Sample Posts

Here's a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>



