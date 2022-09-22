---
nav_order: 7
title: About Digital Collections
---

{%- assign scanners = site.data.equipment -%}

{:#scanners}
## Lab Equipment

An overview of the scanning equipment used in the CDIL. 

### Scanners:

<table class="table">
<tbody>
{% for s in scanners %}
<tr>
<td class="col-4"><img src="{{ s.image | prepend: '/images/' | relative_url }}" alt="image of {{ s.image }}" class="img-fluid"/></td>
<td class="col-8">{{ s.text }}</td>
</tr>
{% endfor %}
</tbody>
</table>

{% include template/credits.html %}