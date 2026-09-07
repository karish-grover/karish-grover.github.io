---
layout: page
permalink: /news/
title: News
description: Research, awards, and professional updates.
nav: true
nav_order: 7
---
<!-- _pages/news.md -->
<div class="news">
    {% if site.news != blank -%} 
        {%- assign news = site.news | reverse -%}
        <ul class="news-list news-list--archive">
          {% for item in news %}
            <li class="news-item">
              <span class="news-date">{{ item.date | date: "%b %-d, %Y" }}</span>
              <span class="news-content">
                {% if item.inline -%}
                  {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
                {%- else -%}
                  <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
                {%- endif %}
              </span>
            </li>
          {%- endfor %}
        </ul>
    {%- else -%} 
        <p>No news so far...</p>
    {%- endif %} 
</div>
