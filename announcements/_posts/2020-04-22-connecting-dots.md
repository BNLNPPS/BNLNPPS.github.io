---
title: Connecting the Dots 2020, Princeton, April 22-24 2020
author: Torre Wenaus
layout: newsletter
symbol: glyphicon-calendar
link: /announcements.html
teams: reconstruction
until: 2020-07-31
---

For more information see [here](https://indico.cern.ch/event/831165/).

<p>
{% for item in site.data.assets reversed %}
    {% if item.venue == "Connecting the Dots 2020, Princeton, April 22-24 2020" %}
        &nbsp; &nbsp; &nbsp; &nbsp; <a href="{{item.name}}" target="_blank">{{item.title}}</a><br>
    {% endif %}
{% endfor %}
</p>
