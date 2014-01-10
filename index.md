---
layout: page
title: Hello World!
tagline: Getting Set up
---
{% include JB/setup %}

## Recent Posts

<ul>
  {% for post in site.posts limit 2 %}
    <li>
      <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>





