---
layout: single
title: "Research"
permalink: /research/
---

{% include base_path %}

## Working Papers
{% assign wps = site.publications | where: "status", "working-paper" | sort: "date" | reverse %}
{% for post in wps %}
  {% include archive-single.html %}
{% endfor %}

## Work in Progress
{% assign wip = site.publications | where: "status", "wip" | sort: "date" | reverse %}
{% for post in wip %}
  {% include archive-single.html %}
{% endfor %}
