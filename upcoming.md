---
layout: page
title: Upcoming events
permalink: /upcoming/
---

<div class="events">
  {% for category in site.categories %}
    {% if category[0] == "upcoming" %}
      {% for event in category[1] reversed %}
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
