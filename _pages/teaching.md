---
layout: single
title: "Teaching"
permalink: /teaching/
---

{% include base_path %}

{% assign groups_by_role = site.teaching | sort: "weight" | group_by: "role" %}
{% for role_group in groups_by_role %}
  {% assign groups_by_inst = role_group.items | group_by: "institution" %}
  {% for inst_group in groups_by_inst %}
### {{ role_group.name }}, {{ inst_group.name }}
<ul>
  {% assign courses = inst_group.items | sort: "weight" %}
  {% for c in courses %}
  <li>
    <strong>{{ c.title }}</strong>
    {% if c.terms %} — {{ c.terms | join: ", " }}{% endif %}
    {% if c.syllabus %} · <a href="{{ c.syllabus | relative_url }}">Syllabus</a>{% endif %}
    {% if c.evals %} · <a href="{{ c.evals | relative_url }}">Evaluations</a>{% endif %}
    {% if c.materials %} · <a href="{{ c.materials | relative_url }}">Materials</a>{% endif %}
  </li>
  {% endfor %}
</ul>
  {% endfor %}
{% endfor %}
