---
layout: page
title: "Parts inventory"
permalink: /parts/
eyebrow: "Bill of materials"
lede: "Every part in the assembly with its file name, quantity, and what it does. Ten unique IDs in the BOM. The track link and rivet entries (P-07 and P-08) ship as extras to the structural BOM since they reach 148 and 150 units."
---

<div class="tbl-wrap">
  <table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Part</th>
        <th>File</th>
        <th class="num">Qty</th>
        <th>Sheet</th>
      </tr>
    </thead>
    <tbody>
      {% for p in site.data.parts %}
      <tr>
        <td data-label="ID"><code>{{ p.id }}</code></td>
        <td data-label="Part"><strong>{{ p.name }}</strong></td>
        <td data-label="File"><code>{{ p.file }}</code></td>
        <td data-label="Qty" class="num">{{ p.qty }}</td>
        <td data-label="Sheet">{% if p.drawing_sheet %}<a href="{{ '/drawings/sheet-' | append: p.drawing_sheet | append: '/' | relative_url }}">Sheet {{ p.drawing_sheet }}</a>{% else %}-{% endif %}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

<h2>Per part detail</h2>

{% for p in site.data.parts %}
<section class="prose" style="border-top: 1px solid #DCE0D8; padding-top: 2rem; margin-top: 2rem;">
  <h3 style="margin-bottom: 0.25rem;">{{ p.name }} <code style="font-size: 0.85rem; color: #8B9499; margin-left: 0.5rem;">{{ p.id }}</code></h3>
  <dl class="kv">
    <dt>File</dt><dd><code>{{ p.file }}</code></dd>
    <dt>Quantity</dt><dd>{{ p.qty }}</dd>
    <dt>System</dt><dd>{{ p.group | capitalize }}</dd>
    {% if p.drawing_sheet %}<dt>Drawing</dt><dd><a href="{{ '/drawings/sheet-' | append: p.drawing_sheet | append: '/' | relative_url }}">Sheet {{ p.drawing_sheet }}</a></dd>{% endif %}
  </dl>
  <p>{{ p.description }}</p>
</section>
{% endfor %}
