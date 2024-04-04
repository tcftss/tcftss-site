---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<div class="home">

  <h1 class="page-heading" id="latest-ep">Latest Episode</h1>
   <div class="episode-list">
      {% assign episodes = site.episodes | sort: 'date' | reverse %}
        {% for page in episodes %}
          {% if forloop.first == true %}
          <div class="latest-episode">
          <div class="episode-info">
            <a href="{{ page.url | prepend: site.baseurl }}" class="latest-image"><img src="{{ site.basurl }}/assets/episode-image/{{ page.image }}" class="episode-image"></a>
            <div class="episode-text">
              <h4 class="page-heading"> {{ page.title }} </h4>
              <p class="episode-record"><span class="highlight">Episode {{ page.episode }} | {{ page.date | date: '%B %d, %Y' }}</span></p>
              <p class="episode-blurb"> {{ page.description | | truncatewords: 50 }}</p>
              <div class="episode-download">
              <a class="listen" href="{{ page.url | prepend: site.baseurl }}">Listen</a> | <a class="download" href="{{page.link}}"> Download</a> 
            </div>
            </div>
          </div>
          <div class="episode-track">{{ page.content }}</div>
          </div>
          <h4 class="page-heading full-width"> More Episodes </h4>
          {% else %}
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
        {% endif %}
        {% endfor %}
        </div>