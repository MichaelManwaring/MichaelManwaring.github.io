---
layout: post
title: Portfolio
permalink: /portfolio/
---


<section>
	{% for post in site.posts limit:1 %}
	{% if post.categories contains 'portfolio' %}
	<header class="major">
		<h2>{{ post.title }}</h2>
		<p class="post-meta">{{ post.date | date: "%b %-d, %Y" }}{% if post.author %} • {{ post.author }}{% endif %}{% if page.meta %} • {{ page.meta }}{% endif %}</p>
	</header>

	<section>
		{{ post.content }}
	</section>

	{% endif %}
	{% endfor %}
</section>
<section>
	<div class="row">
		{% for post in site.posts offset:1 %}
		{% if post.categories contains 'portfolio' %}

		<article class="{% cycle '6u', '6u$' %} 12u(small)">
			<header>
				<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
			</header>
			<section>
				{{ post.excerpt }}
			</section>
			<footer>
				<ul class="actions">
					<li><a href="{{ post.url }}" class="button">Read More</a></li>
				</ul>
			</footer>
		</article>
		{% endif %}
		{% endfor %}
	</div>
</section>
