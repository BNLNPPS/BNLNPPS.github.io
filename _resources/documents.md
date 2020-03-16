---
title: Documents
layout: default
---

Documents and presentations with NPPS (co)authorship

## Documents

<ul>
{% for item in site.data.assets reversed %}
  {% if item.type == 'document' or item.name contains "/assets/documents" %}
    {% if item.date %}
        {% assign itemdate = item.date | string_to_date | date: "%Y-%m-%d" %}
    {% else %}
        {% assign itemdate = item.name | remove: "/assets/documents/" | string_to_date | date: "%Y-%m-%d" %}
    {% endif %}

    <li><a href="{{item.name}}" target="_blank">{{item.title}}</a>, &nbsp;
    
    <!-- horrible, but liquid has no named element arrays or dicts -->
    {% for person in site.data.people %}
    <!-- mxp: disabled the author field since there are multiple and I will need to revisit later -->
      {% if person.name == item.author and false %}
        <a href="/people/{{person.name}}">{{ person.full }}</a>, {{ item.date | date: "%b %Y" }}
      {% endif %}
    {% endfor %}
  {% if item.venue.size > 0 %}
    {{ item.venue }},
  {% endif %}

    &nbsp; {{ itemdate | date: "%b %Y" }}
    
    </li>
  {% endif %}
{% endfor %}
</ul>

## Presentations

<ul>
{% for item in site.data.assets reversed %}
  {% if item.type == 'slides' or item.name contains "/assets/slides" %}

    {% if item.date %}
        {% assign itemdate = item.date | string_to_date | date: "%Y-%m-%d" %}
    {% else %}
        {% assign itemdate = item.name | remove: "/assets/slides/" | string_to_date | date: "%Y-%m-%d" %}
    {% endif %}

    <li><a href="{{item.name}}" target="_blank">{{item.title}}</a>, &nbsp;

<!--

  {% assign authors = item.author | split: " " %}
  {% for author in authors %}
    {% for person in site.data.people %}
      {% if person.name == author %}
        <a href="/people/{{person.name}}">{{ person.full }}</a> &nbsp; 
      {% endif %}
    {% endfor %}
  {% endfor %}

-->

  {% if item.venue.size > 0 %}
    {{ item.venue }},
  {% endif %}

    &nbsp; {{ itemdate | date: "%b %Y" }}
    </li>
  {% endif %}
{% endfor %}
</ul>
