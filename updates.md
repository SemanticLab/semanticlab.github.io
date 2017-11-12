---
layout: default
title: Updates
permalink: /updates/
---


<h1 class="page-heading">Updates</h1>

<div class="updates">
	{% for update in site.categories.updates %}
		<article class="updates-article">
			<h4 class="updates-title">{{update.date | date_to_long_string}} - {{update.title}}</h4>
			<p>{{update.content}}</p>
		</article>
	{% endfor %}
</div>