{% from "components/pdf.njk" import pdf %}
{% set title="Lecture 1" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf("lec01a.pdf", "lec") }}

_administrative info only_
