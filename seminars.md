---
title: BNL Physics Software and Computing Seminar Series
layout: default
---

# BNL Physics Software and Computing Seminar Series

The [Nuclear and Particle Physics Software (NPPS) Group](http://npps.bnl.gov/) and [RHIC ATLAS Computing Facility (RACF)](https://www.racf.bnl.gov/) in the BNL Physics Department jointly organize a seminar series on software and computing topics of interest to the HEP and NP communities.

[Seminar agendas](https://indico.bnl.gov/category/264/)

<p>
Seminars to date:
{% for item in site.data.assets reversed %}

  {% if item.venue == "BNL Physics S&C Seminar Series" %}

    {% if item.date %}
        {% assign date = item.date | string_to_date | date: "%Y-%m-%d" %}
    {% else %}
        {% assign date = item.name | remove: "/assets/documents/" | string_to_date | date: "%Y-%m-%d" %}
    {% endif %}

    <br> &nbsp; &nbsp; <a href="{{item.name}}" target="_blank">{{item.title}}</a>,
    &nbsp; {{ item.author }},
    &nbsp; {{ date | date: "%b %Y" }}
  {% endif %}
{% endfor %}
</p>
