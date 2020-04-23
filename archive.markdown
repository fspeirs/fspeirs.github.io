---
layout: page
title: Archive
permalink: /archive/
---

This page contains an archive of selected posts from my blog that I think are worth preserving.

I ran the world's first 1:1 iPad programme in my school in 2010 and the posts from that year made me quite famous for a while.

The summaries on this page were written more recently to explain why I thought the post was worth keeping around.

Almost all of the technical details in these posts are surely now obsolete so they are preserved mostly out of historical interest.

<ul id="archivelist">
{% for page in site.archive %}
  <li class="archiveitem">
	<a href="{{ page.url }}">{{page.date | date: '%Y-%m-%d'}} - {{ page.title }}</a><br>
	<i>{{page.summary}}</i>         
  </li>
{% endfor %}
</ul>