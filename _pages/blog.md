---
layout: academic
title: Writing
permalink: /blog/
description: Notes on machine learning, natural language processing, and distributed systems by Abrar Eyasir.
---
<p class="eyebrow">Notes &amp; explanations</p>
<h1>Writing</h1>
<p class="writing-intro">Exploring machine learning, language models, and the systems behind them.</p>
<a href="https://medium.com/@eyasir2047">More writing on Medium ↗</a>
<ul class="writing-list">
{% for post in site.posts %}
  <li><time class="date" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%B %d, %Y' }}</time><h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2><div>{{ post.excerpt }}</div><a href="{{ post.url | relative_url }}">Read article →</a></li>
{% endfor %}
</ul>
