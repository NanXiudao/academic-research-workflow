{% bq %}
[!quote] {% if zt.pageLabel and zt.pageLabel != "" %}PDF Highlight · Page {{ zt.pageLabel }}{% else %}PDF Highlight{% endif %}

{{ zt.imgLink | embed }}{{ zt.text }}

{% if zt.comment %}
**💭 Note**

{{ zt.comment }}

{% endif %}
[📄 Open PDF]({{ zt.backlink }}){% if zt.citation %} · {{ zt.citation }}{% endif %}
{% endbq %}
