---
title: "NPPS news"
layout: default
---

<h1>{{ page.title }}</h1>

<div>

</div>

<div class="row">

{% for post in site.categories.announcements %}

<div class="blog-post">
<h3 class="blog-post-title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
<p class="blog-post-meta">{{ post.date | date_to_string }} by <a href="{{ post.url }}">{{ post.author }}</a></p>

{{ post.content  }}

</div>

{% endfor %}

</div>
