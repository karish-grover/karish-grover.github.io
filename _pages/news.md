---
layout: page
permalink: /news/
title: news
description: all news reversed chronological order.
nav: true
nav_order: 7
---
<!-- _pages/news.md -->
<div class="news">
    {% if site.news != blank -%} 
        {%- assign news_size = site.news | size -%}
        <div class="table-responsive">
            <table class="table table-sm table-borderless">
                {%- assign news = site.news | reverse -%}
                {% for item in news %}
                    <tr>
                        <th class = "news th" scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
                        <td>
                            {% if item.inline -%} 
                                {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
                            {%- else -%} 
                                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
                            {%- endif %} 
                        </td>
                    </tr>
                {%- endfor %} 
            </table>
        </div>
    {%- else -%} 
        <p>No news so far...</p>
    {%- endif %} 
</div>
