---
layout: page
title: Episodes
permalink: /episodes/
---
<!-- <ul class="pod-list">
{% assign episodes = site.episodes | sort: 'episode' | reverse %}
{% for page in episodes %}
	<li>
	<h4 class="page-heading"> {{ page.title }} | Episode {{ page.episode }} </h4>
	<a href="{{ page.url | prepend: site.baseurl }}"><img src="{{ site.basurl }}/assets/episode-image/{{ page.image }}" class="episode-image"></a>
		{{ page.content }}
		<p class="pod-date"><small> Recorded on {{ page.date | date: '%B %d, %Y' }} </small></p>
	</li>
{% endfor %}
</ul> -->



<div class="episode-list">
	{% assign episodes = site.episodes | sort: 'episode' | reverse %}
		{% for page in episodes %}
		<div class="episode-card">
			<a href="{{ page.url | prepend: site.baseurl }}"><img src="{{ site.basurl }}/assets/episode-image/{{ page.image }}" class="episode-image"></a>
			<div class="episode-info">
				<h4 class="page-heading"> {{ page.title }} </h4>
				<p class="episode-record"><span class="highlight">Episode {{ page.episode }} | {{ page.date | date: '%B %d, %Y' }}</span></p>
				<p class="episode-blurb"> {{ page.description | | truncatewords: 25 }}</p>
			</div>
			<div class="episode-download">
				<a class="listen" href="{{ page.url | prepend: site.baseurl }}">Listen</a> | <a class="download" href="{{page.link}}"> Download</a> 
			</div>
			</div>
		{% endfor %}

