---
layout: page
permalink: /teaching/
title: Teaching
description: 
nav: true
nav_order: 6
---

<!-- pages/teaching.md -->
<div class="teaching">
{% if site.teaching != blank -%} 
<div class="table-responsive">
    <table class="table table-sm table-borderless">
    {%- assign teaching = site.teaching | reverse -%} 
    {% for item in teaching %} 
    <tr>
        <th scope="row">{{ item.sem }}</th>
        <td>
        {% if item.inline -%} 
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
        {%- else -%} 
            <a class="teaching-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
        {%- endif %} 
        </td>
        <td>
        {% if item.place -%} 
            <span class="teaching-place">{{ item.place }}</span>
        {%- endif %}
        </td>
    </tr>
    {%- endfor %} 
    </table>
</div>
{%- else -%} 
<p>No teaching so far...</p>
{%- endif %} 
</div>
