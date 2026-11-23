# {{ zt.title }}

<div style="display:flex;flex-wrap:wrap;gap:8px;margin:10px 0 14px;align-items:center;">
  <span style="padding:4px 11px;border-radius:20px;background:#5578dd25;color:#8daaff;font-size:12px;font-weight:600;">{{ zt.date | date: "%Y" }}</span>
  {% for tag in zt.tags %}
  <span style="padding:4px 11px;border-radius:20px;background:#38a58b20;color:#68c5a7;font-size:12px;font-weight:500;">{{ tag.name }}</span>
  {% endfor %}
</div>

[Zotero]({{ zt.backlink }}) {{ zt.attachments | map: "fileLink" | compact | join: " " }}

## Abstract

{{ zt.abstract }}

## Research Question

## Methodology

## Experiments

## PDF Annotations

```zotquery
views:
  - type: annotations
    name: Annotations
    from: annotations
    filters: item == this.item
    sort:
      - property: attachment.dateAdded
        direction: ASC
      - property: sortIndex
        direction: ASC
```
