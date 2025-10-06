---
layout: single
title: "Research"
permalink: /research/
---

{% include base_path %}

## Working Papers
{% assign wps = site.publications | where: "status", "working-paper" | sort: "weight" %}
{% if wps.size == 0 %}_No working papers yet._{% endif %}
{% for p in wps %}
<div class="archive__item">
  <h3 class="archive__item-title">{{ p.title }}</h3>  <!-- plain text (no link) -->
  {% if p.authors %}<p><em>{{ p.authors }}</em></p>{% endif %}
  {% if p.excerpt %}<p>{{ p.excerpt }}</p>{% endif %}
  <p>
  {% if p.paperurl %}
    <a href="{{ p.paperurl | relative_url }}" class="btn">Download Paper</a>
  {% elsif p.coming_soon %}
    <span class="btn" aria-disabled="true" style="pointer-events:none;opacity:.65;">
      Draft coming soon
    </span>
  {% endif %}
</p>
</div>
<hr/>
{% endfor %}

## Work in Progress
{% assign wip = site.publications | where: "status", "wip" | sort: "weight" %}
{% if wip.size == 0 %}_No works in progress listed yet._{% endif %}
{% for p in wip %}
<div class="archive__item">
  <h3 class="archive__item-title">{{ p.title }}</h3>
  {% if p.authors %}<p><em>{{ p.authors }}</em></p>{% endif %}
  {% if p.excerpt %}<p>{{ p.excerpt }}</p>{% endif %}
</div>
<hr/>
{% endfor %}
