# ZotLit annotation template (reference draft)

**Status:** Reference only. The original exact working template was not preserved. Back up your current ZotLit Template Workbench → 标注 template before editing.

The following is a structural example of the desired Markdown callout. Adapt it to the actual `{% bq %}` behavior and field syntax supported by your installed ZotLit 2.2 version.

```liquid
{% bq %}
[!quote] PDF Highlight · Page {{zt.pageLabel}}

{{zt.text}}

[📄 Open PDF]({{zt.backlink}}) · {{zt.citation}}
{% endbq %}
```

Optional fields previously used include `zt.comment` and `zt.imgLink`. The placement and rendering of image annotations require local validation.

Do not assume this reference draft exactly matches the working template that was used in Obsidian.
