---
title: NPPS Who's Who
layout: default
abbrev: who
weight: 20
---

<h1> Who we are </h1>

<br>
<p>
Group leader: <a href="/people/wenaus.html">Torre Wenaus</a>
</p>

<h2>NPPS leadership team</h2>

<table width="100%">
{% for who in site.people %}
{% if who.tags contains 'leader' %}
{% include persondetails_updated.md %}
{% endif %}
{% endfor %}
</table>

<h2>NPPS group members</h2>

<table width="100%">
{% for who in site.people %}
{% if who.tags contains 'member' %}
{% include persondetails_updated.md %}
{% endif %}
{% endfor %}
</table>

<h2>NPPS collaborators</h2>

<table width="100%">
{% for who in site.people %}
{% if who.tags contains 'collaborator' %}
{% include persondetails_updated.md %}
{% endif %}
{% endfor %}
</table>

