---
layout: blog
title: Blog
nocitationtext: true 
permalink: /blog/
---


<div class="container">
  <div class="content">

	<h1 class="page-heading">Blog Posts</h1>

	<div class="updates">
		<ul>
			{% for blog in site.categories.blog %}
				<li>{{blog.date | date_to_long_string}} - <a href="{{site.url}}{{blog.url}}">{{blog.title}} {{blog.subtitle}} -- {{blog.description}}</a></li>


			{% endfor %}
		</ul>
	</div>
  </div>
</div>