---
title: poster presentations
layout: page
permalink: "/poster/"
description: publications by categories in reversed chronological order.
nav: false
---

<div class="publications">

  <h4>Poster presentations (total {% bibliography_count -f papers -q @inproceedings[booktitle~=(poster)] %})</h4>
{% for y in site.data.globalvar.years %}
  {% capture articles %}
  {% bibliography_count -f papers -q @inproceedings[year={{y}} && booktitle~=(poster)] %}
  {% endcapture %}
  {% assign numarticles = articles | times: 1 %}
  {% if numarticles > 0 %}
    <h2 class="year">{{y}}</h2>
  {% endif %}
  {% bibliography -f papers -q @inproceedings[year={{y}} && booktitle~=(poster)] %}
{% endfor %}
 
</div>