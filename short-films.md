---
layout: page
title: Filmography
description: Short film work
nav: true
header-img: uneventful/images/header_laurel.jpg
nav-order: 5
---

Credits: director, director of photography, writer, editor, and visual effects compositor, among other things.

<h2> Short Films</h2>
{% assign short-films = site.short-films | sort: 'production-date' | reverse %}
{% for short-film in short-films %}
{% if short-film.layout == 'film' and (short-film.published == null or short-film.published == true)  %}
<div class="row">


  <div class="col-sm-4">
    <a href="{{ short-film.url }}"><img class="img-responsive" src="{{ short-film.url }}/{{ short-film.thumbnail }}"></a>
  </div>
    <div class="col-sm-8">
      <h3 class="text-uppercase" style="margin-top: 3px;"><a href="{{ short-film.url }}">{{ short-film.title }}</a><span class=""> ({{ short-film.production-year }})</span></h3>
  {% if short-film.synopsis %}<p>Synopsis: <strong>{{ short-film.synopsis }}</strong></p>{% endif %}
  {% if short-film.running-time %}<p>Running time: <strong>{{ short-film.running-time }}</strong></p>{% endif %}
  {% if short-film.budget %}<p>Budget: <strong>{{ short-film.budget }}</strong></p>{% endif %}
  {% if short-film.production %}<p>Production: <strong>{{ short-film.production }}</strong></p>{% endif %}
  {% if short-film.alt-title %}<p>Alternative title: <strong>{{ short-film.alt-title }}</strong></p>{% endif %}
  </div>
  </div>
  <hr>
  {% endif %}
{% endfor %}
