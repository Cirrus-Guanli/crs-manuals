---
section_id: "120"
section_title: Glossary
---

Unless otherwise noted, all terms used by the Community Rating System (CRS) are the same as those defined in the National Flood Insurance Program Rules and Regulations (44 Code of Federal Regulations §59.1).

{% assign sortedGlossary = glossary | sort: "term" %}

<dl class="glossary">
{% for entry in sortedGlossary %}
<dt id="{{ entry.term | slugify }}">{{ entry.term }}</dt>
<dd>
{{ entry.definition }}
{# entry.definition | md_first_inline #}
{% if entry.subdefinitions %}
<dl class="subdefinitions">
{% for sub in entry.subdefinitions %}
  <dt>{{ sub.term }}</dt>
  <dd>{{ sub.definition }}</dd>
  {% comment %}<dd>{{ sub.definition | md_first_inline }}</dd>{% endcomment %}
{% endfor %}
</dl>
{% endif %}
</dd>
{% endfor %}
</dl>
