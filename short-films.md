---
layout: page-with-slider
title: Filmography
description: List of short film work by Fahdi Kanavati
nav: true
header-imgs:
 - link: uneventful/images/uneventful_still2_thumb.png
 - link: play-along-alice/images/PlayAlong_Still13_thumb.png
 - link: play-along-alice/images/PlayAlong_Still3_thumb.png
 - link: the-stage/images/the_stage_still5_thumb.png
 - link: a-favour/images/a_favour_still1_thumb.png
 - link: uneventful/images/uneventful_still5_thumb.png
nav-order: 5
---

Credits: director, director of photography, writer, editor, and visual effects compositor, among other things.

<h2> Short Films</h2>
{% assign short-films = site.short-films | sort: 'production-date' | reverse %}
<div class="row">
{% for short-film in short-films %}
{% if short-film.layout == 'film' and (short-film.published == null or short-film.published == true)  %}
<div class="col-sm-6 panel-outer">
<div class="panel-inner">

<div class="image">
    <a href="{{ short-film.url }}"><img class="img-responsive" src="{{ short-film.url }}/{{ short-film.thumbnail }}"></a>
  </div>
    <div class="col-xs-12 panel-content">
      <h3 class="text-uppercase" style="margin-top: 3px;"><a href="{{ short-film.url }}">{{ short-film.title }}</a><span class=""> ({{ short-film.production-year }})</span></h3>
  {% if short-film.synopsis %}<p>Synopsis: <strong>{{ short-film.synopsis }}</strong></p>{% endif %}
  {% if short-film.running-time %}<p>Running time: <strong>{{ short-film.running-time }}</strong></p>{% endif %}
  {% if short-film.budget %}<p>Budget: <strong>{{ short-film.budget }}</strong></p>{% endif %}
  {% if short-film.production %}<p>Production: <strong>{{ short-film.production }}</strong></p>{% endif %}
  {% if short-film.alt-title %}<p>Alternative title: <strong>{{ short-film.alt-title }}</strong></p>{% endif %}
  </div>
  </div>
</div>
  {% endif %}

{% endfor %}
  </div>

<style>
  .panel-content {
    padding-bottom: 20px;
     background-color: #f9f9f9;
  }
  .panel-outer {
    margin-top: 10px;

  }
  .panel-content h3 {
    padding-top: 10px;
  }
  .panel-content p{
    margin: 0 0 2px;
    font-size:14px;
  }
</style>
