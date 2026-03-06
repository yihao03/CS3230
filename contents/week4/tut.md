{% from "components/pdf.njk" import pdf %}
{% set tutorialNum="tutorial04" %}
{% set title="Tutorial 4" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf(tutorialNum + "-questions.pdf", "tut") }}

## Slides

{{ pdf(tutorialNum + "-slides.pdf", "tut") }}

<div id="solution">

## Solution

{{ pdf(tutorialNum + "-answers.pdf", "tut") }}

</div>
