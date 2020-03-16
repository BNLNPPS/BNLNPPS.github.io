    <!-- horrible, but liquid has no named element arrays or dicts -->
    {% for person in site.data.people %}
    <!-- mxp: disabled the author field since there are multiple and I will need to revisit later -->
      {% if person.name == item.author and false %}
        <a href="/people/{{person.name}}">{{ person.full }}</a>, {{ item.date | date: "%b %Y" }}
      {% endif %}
    {% endfor %}
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
