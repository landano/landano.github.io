---
title: Sitemap
date: 2025-05-11 10:00:00 Z
permalink: "/sitemap/"
layout: basic
header_transparent: false
description: A complete list of all pages on the Landano website
sitemap: false
---

# Sitemap

A complete list of all pages on the Landano website.

## Main Pages

<ul>
{% for item in site.pages %}
  {% if item.title and item.title != "" and item.layout != "redirect" and item.sitemap != false %}
    <li>
      <a href="{{ site.baseurl }}{{ item.url }}">{{ item.title }}</a>
      {% if item.description %}<p><small>{{ item.description }}</small></p>{% endif %}
    </li>
  {% endif %}
{% endfor %}
</ul>

## Blog Posts

<ul>
{% for post in site.posts %}
  <li>
    <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    <span>({{ post.date | date: "%B %-d, %Y" }})</span>
    {% if post.description %}<p><small>{{ post.description }}</small></p>{% endif %}
  </li>
{% endfor %}
</ul>

## Projects

<ul>
{% for project in site.projects %}
  <li>
    <a href="{{ site.baseurl }}{{ project.url }}">{{ project.title }}</a>
    {% if project.description %}<p><small>{{ project.description }}</small></p>{% endif %}
  </li>
{% endfor %}
</ul>

## Services

<ul>
{% for service in site.services %}
  <li>
    <a href="{{ site.baseurl }}{{ service.url }}">{{ service.title }}</a>
    {% if service.description %}<p><small>{{ service.description }}</small></p>{% endif %}
  </li>
{% endfor %}
</ul>

## Team Members

<ul>
{% for member in site.team %}
  <li>
    <a href="{{ site.baseurl }}{{ member.url }}">{{ member.title }}</a>
    {% if member.jobtitle %}<span> - {{ member.jobtitle }}</span>{% endif %}
  </li>
{% endfor %}
</ul>

## Categories

<ul>
{% for category in site.categories %}
  {% capture category_name %}{{ category | first }}{% endcapture %}
  <li>
    <a href="{{ site.baseurl }}/category/{{ category_name | slugify }}">{{ category_name }}</a>
    <span>({{ site.categories[category_name].size }} posts)</span>
  </li>
{% endfor %}
</ul>