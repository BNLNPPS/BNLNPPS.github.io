{% assign item=include.item %}
{% if item.date %}
{% assign itemdate = item.date | string_to_date | date: "%Y-%m-%d" %}
{% else %}
{% assign itemdate = item.name | remove: "/assets/slides/" | string_to_date | date: "%Y-%m-%d" %}
{% endif %}

<li>
<a href="{{item.name}}" target="_blank">{{item.title}}</a>: &nbsp;

{% assign authors = item.author | split: " " %}
{% for author in authors %}
{% for person in site.data.people %}
{% if person.name == author %}
<a href="/people/{{person.name}}">{{ person.full }}</a>, &nbsp; 
{% endif %}
{% endfor %}
{% endfor %}



{% if item.venue.size > 0 %}
{{ item.venue }},
{% endif %}
&nbsp; {{ itemdate | date: "%b %Y" }}
</li>

