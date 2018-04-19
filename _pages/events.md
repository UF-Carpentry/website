---
layout: single
permalink: /events/
title: Workshops and Other Events
classes: wide
---

Here are our upcoming events
{%for event in site.events reversed %}
    {% unless event.next %}
        <h1>{{ event.start | date: '%Y' }}</h1>
        <ul>
    {% else %}
        {% capture year %}{{ event.start | date: '%Y' }}{% endcapture %}
        {% capture nyear %}{{ event.next.start | date: '%Y' }}{% endcapture %}
        {% if year != nyear %}
            </ul>
            <h1>{{ event.start | date: '%Y' }}</h1>
            <ul>
        {% endif %}
    {% endunless %}
    <li><a href="{{ site.baseurl}}{{ event.url }}">{{ event.start | date: "%b %-d" }} - {{ event.title }}</a></li>
{% endfor %}
</ul>