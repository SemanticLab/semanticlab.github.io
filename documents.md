---
layout: default
title: Publications
permalink: /publications/
---


<h1 class="page-heading">Publications</h1>

<div class="documents">
	{% for document in site.categories.documents %}
		<article class="documents-article">
			<h4 class="documents-title">{{document.date | date_to_long_string}} - {{document.title}}</h4>
			<p>{{document.content}}</p>
			<h3><a href="{{document.link}}">View</a></h3>
		</article>
	{% endfor %}
</div>