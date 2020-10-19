---
layout: default
title: People
permalink: /people/
---


<h1 class="page-heading">People</h1>

<div class="people-table">
		<table>
		<tbody>

			{% for member in site.data.people_team %}
			  <tr>
			  	<td>{% if member.name %}{{ member.name }}{% endif %}</td>
			  	<td>{% if member.role %}{{ member.role }}{% endif %}</td>
			  	<td>{% if member.email %}<a href="mailto:{{ member.email }}">email</a>{% endif %}</td>
			  	<td>{% if member.twitter %}<a href="https://twitter.com/{{ member.twitter }}">twitter</a>{% endif %}</td>
			  	<td>{% if member.github %}<a href="https://github.com/{{ member.github }}">github</a>{% endif %}</td>
			  	<td>{% if member.website %}<a href="{{ member.website }}">website</a>{% endif %}</td>
			  </tr>
			{% endfor %}
		</tbody>
	</table>
</div>

<br/>

<b>Past Student Members of the Semantic Lab at Pratt:</b><br>
Meghan Lyon, Taylor Baker, Rachel Egan, Andreas Jonathan, Dana Lachenmayer, Mary Mann, Hannah Sistrunk, Eric Toole <br>
<i>For past members of the Linked Jazz project, click <a href="https://linkedjazz.org/?page_id=215">here</a>.</i>

   

<!-- 
This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)

You can find the source code for Minima at GitHub:
[jekyll][jekyll-organization] /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at GitHub:
[jekyll][jekyll-organization] /
[jekyll](https://github.com/jekyll/jekyll)


[jekyll-organization]: https://github.com/jekyll
 -->
