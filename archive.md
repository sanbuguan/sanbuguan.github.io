---
layout: page
title: "Archive"
description: "你看到的，是我所有文章的汇总"
header-img: "img/orange.jpg"
---


<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator" style=" font-weight: bolder;font-size: large;">{{ y }}</li>
  {% endif %}
  {% if  post.hidden != true %}
    <li class="listing-item">
      <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
      <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endif %}
  
{% endfor %}
</ul>