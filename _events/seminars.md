---
title: BNL Physics Software and Computing Seminar Series
layout: default
---
{% comment %}

This page will need more work, and perhaps the schema of "assets" needs
to be updated for cleaner logic. I fixed the date handling a little bit. -mxp-

{% endcomment %}

# BNL Physics Software and Computing Seminar Series

The [Nuclear and Particle Physics Software (NPPS) Group](http://npps.bnl.gov/) and [RHIC ATLAS Computing Facility (RACF)](https://www.racf.bnl.gov/) in the BNL Physics Department jointly organize a seminar series on software and computing topics of interest to the HEP and NP communities.

[Seminar agendas](https://indico.bnl.gov/category/264/)

<p>
Seminars to date:
{% for item in site.data.assets reversed %}

{% if item.venue == "BNL Physics S&C Seminar Series" %}
{% assign date = '' %}
{% if item.date %}
{% assign date = item.date | string_to_date | date: "%Y-%m-%d" %}
{% else %}
{% if item.name contains "/assets/documents/" %}
{% assign date = item.name | remove: "/assets/documents/" | string_to_date | date: "%Y-%m-%d" %}
{% endif %}
{% endif %}

<br> &nbsp; &nbsp; <a href="{{item.name}}" target="_blank">{{item.title}}</a>,
&nbsp; 
{% if item.authorfull.size > 0 %}
{{ item.authorfull }},
{% else %}
{{ item.author }},
{% endif %}
&nbsp; {{ date | date: "%b %Y" }}
{% endif %}
{% endfor %}
</p>
