---
layout: page
title: Archive
permalink: /blog/
---

This is my archive page.

<ul id="archivelist">
{% for page in site.archive %}
  <li class="archiveitem">
	<a href="{{ page.url }}">{{page.date | date: '%Y-%m-%d'}} - {{ page.title }}</a><br>
	<i>{{page.summary}}</i>         
  </li>
{% endfor %}
</ul>