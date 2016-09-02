---
layout: page
title: Hosts
permalink: /hosts/
---
<ul class="pod-hosts">
{% assign hosts = site.hosts | sort: 'title' | reverse %}
{% for page in hosts %}
	<li>
	<div class="pod-host">
	<div class="host-info">
		<img src="/assets/portrait/{{ page.portrait }}" class="pod-portrait">
		<div class="host-links">
			<h4> {{ page.title }} </h4>
			<ul class="social-media-list">
		          {% if page.twitter_username %}
		          <li>
		            {% include icon-twitter.html username=page.twitter_username %}
		          </li>
		          {% endif %}
		          {% if page.instagram %}
		          <li>
		            {% include icon-instagram.html username=page.instagram %}
		          </li>
		          {% endif %}
		          <li>
		          	<a class="" href="{{ page.link }}"><span class="host-site">Site &#8227;</span></a>
		          </li>
		        </ul>
	    </div>
	</div>
	<div class="host-blurb">
		{{ page.content }}
	</div>
		</div>
	</li>
{% endfor %}
</ul>