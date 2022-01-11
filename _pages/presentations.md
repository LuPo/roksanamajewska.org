---
title: oral presentations
layout: page
permalink: "/presentations/"
description: publications by categories in reversed chronological order.
nav: false
---

<div class="publications">

  <h4>Oral presentations (total {% bibliography_count -f papers -q @inproceedings[booktitle~=(oral presentation) || booktitle~=(keynote presentation) ] %})</h4>
{% for y in site.data.globalvar.years %}
  {% capture articles %}
  {% bibliography_count -f papers -q @inproceedings[year={{y}} && booktitle~=(oral presentation)] %}
  {% endcapture %}
  {% assign numarticles = articles | times: 1 %}
  {% if numarticles > 0 %}
    <h2 class="year">{{y}}</h2>
  {% endif %}
  {% bibliography -f papers -q @inproceedings[year={{y}} && booktitle~=(oral presentation) || year={{y}} && booktitle~=(keynote presentation) ] %}
{% endfor %}
 
</div>
