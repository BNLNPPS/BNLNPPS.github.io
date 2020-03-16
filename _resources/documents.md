---
title: Documents
layout: default
---

A collection of documents and presentations with NPPS (co) authorship.

# Documents

<ul>
{% assign all_documents=site.data.assets | where: "type", "document" %}
{% for item in all_documents %}
{% if item.date %}
{% assign itemdate = item.date | string_to_date | date: "%Y-%m-%d" %}
{% else %}
{% assign itemdate = item.name | remove: "/assets/documents/" | string_to_date | date: "%Y-%m-%d" %}
{% endif %}
<li><a href="{{item.name}}" target="_blank">{{item.title}}</a>, &nbsp;
{% if item.venue.size > 0 %}
{{ item.venue }},
{% endif %}
&nbsp;
{{ itemdate | date: "%b %Y" }}
</li>
{% endfor %}
</ul>


{% assign all_slides=site.data.assets | reverse | where: "type", "slides" %}
{% assign chep_slides=all_slides | where: "category", "chep" %}
{% assign npps_slides=all_slides | where: "category", "npps" %}
{% assign misc_slides=all_slides | where: "category", "misc" %}

# Presentations
### CHEP (Computing in High Energy and Nuclear Physics Conference series)
<ul>
{% for item in chep_slides %}
{% include slide_line.md item=item %}
{% endfor %}
</ul>

### Internal NPPS presentations
<ul>
{% for item in npps_slides %}
{% include slide_line.md item=item %}
{% endfor %}
</ul>

### Misc presentations
<ul>
{% for item in misc_slides %}
{% include slide_line.md item=item %}
{% endfor %}
</ul>
