---
nav_order: 3
title: Lab Equipment
anchor_headings: false
---

An overview of the scanning equipment used in the CDIL. 

## Scanners

<table class="table">
<tbody>
{%- assign scanners = site.data.equipment -%}
{% for s in scanners %}
<tr>
<td class="col-4"><img src="{{ s.image | prepend: '/images/' | relative_url }}" alt="image of {{ s.image }}" class="img-fluid"></td>
<td class="col-8"><strong>{{ s.title }}</strong> <br>{{ s.text }} {% if s.manual %}<br><a href="{{ s.manual | relative_url }}">User Manual</a>{% endif %}</td>
</tr>
{% endfor %}
</tbody>
</table>
