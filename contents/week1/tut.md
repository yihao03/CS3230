{% from "components/pdf.njk" import pdf %}
{% set title="Tutorial 1" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf("tutorial01-questions.pdf", "tut") }}

## Slides

{{ pdf("tutorial01-slides.pdf", "tut") }}

<div id="solution">

## Solution

{{ pdf("tutorial01-answers.pdf", "tut") }}

</div>
