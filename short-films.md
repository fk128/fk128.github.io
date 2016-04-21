---
layout: page
title: Filmography
nav: true
nav-order: 5
---

Credits: director, director of photography, writer, editor, and visual effects compositor, among other things.

<h2> Short Films</h2>
{% assign short-films = site.short-films | sort: 'production-date' | reverse %}
{% for short-film in short-films %}
{% if short-film.layout == 'film' and (short-film.published == null or short-film.published == true)  %}
<div class="row">

  <h3 class="text-uppercase"><a href="{{ short-film.url }}">{{ short-film.title }}</a><span class=""> ({{ short-film.production-year }})</span></h3>
  <div class="col-md-4">
    <img class="img-responsive" src="{{ short-film.url }}/{{ short-film.thumbnail }}">
  </div>
    <div class="col-md-8">
  {% if short-film.synopsis %}<p>Synopsis: <strong>{{ short-film.synopsis }}</strong></p>{% endif %}
  {% if short-film.running-time %}<p>Running time: <strong>{{ short-film.running-time }}</strong></p>{% endif %}
   {% if short-film.budget %}<p>Budget: <strong>{{ short-film.budget }}</strong></p>{% endif %}
   {% if short-film.production %}<p>Production: <strong>{{ short-film.production }}</strong></p>{% endif %}
  </div>
  </div>
  <hr>
  {% endif %}
{% endfor %}
