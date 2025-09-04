---
layout: single
title: "Teaching"
permalink: /teaching/
---

{% include base_path %}

## Courses & Roles

{% assign items = site.teaching | sort: "weight" %}
{% if items.size == 0 %}_No teaching listed yet._{% endif %}
{% for t in items %}
<div class="archive__item">
  <h3 class="archive__item-title">{{ t.title }}</h3>
  <p>
    {% if t.role %}<strong>{{ t.role }}</strong>{% endif %}
    {% if t.institution %} · {{ t.institution }}{% endif %}
    {% if t.terms %} · {{ t.terms | join: ", " }}{% elsif t.term %} · {{ t.term }}{% endif %}
  </p>
  {% if t.description %}<p>{{ t.description }}</p>{% endif %}

  <p>
    {% if t.syllabus %}<a href="{{ t.syllabus | relative_url }}" class="btn">Syllabus</a>{% endif %}
    {% if t.evals %}<a href="{{ t.evals | relative_url }}" class="btn">Evaluations</a>{% endif %}
    {% if t.materials %}<a href="{{ t.materials | relative_url }}" class="btn">Materials</a>{% endif %}
  </p>
</div>
<hr/>
{% endfor %}
