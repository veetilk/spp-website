---
layout: page
title: Activities
permalink: /activity/
---

<div class="events">
  {% for category in site.categories %}
    {% if category[0] == "activities" %}
      {% for event in category[1] %}
        <article class="event">
          <h1>{{ event.title }}</h1>
          {% if event.content contains site.excerpt_separator %}
            <div class="entry">
              {{ event.excerpt }}
            </div>
            <a href="{{ site.baseurl }}{{ event.url }}" class="read-more">Read More</a>
          {% else %}
            <div class="entry">
              {{ event.content }}
            </div>
          {% endif %}
        </article>
      {% endfor %}
    {% endif %}
  {% endfor %}
</div>
