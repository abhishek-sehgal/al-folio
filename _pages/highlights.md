---
layout: page
title: highlights
permalink: /highlights/
description: professional news and highlights
nav: false
---

<div class="news">
    <div class="table-responsive">
        <table class="table table-sm table-borderless">
        {% assign news = site.news | reverse %}
        {% for item in news %}
        <tr>
            <th scope="row"><a class="badge">{{ item.date | date: "%b %d, %Y" }}</a></th>
            <td>
            {% if item.inline %}
                {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {% elsif item.redirect %}
                <a href="{{ item.redirect }}">{{ item.title }}</a>
            {% else %}
                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {% endif %}
            </td>
        </tr>
        {% endfor %}
        </table>
    </div>
</div>