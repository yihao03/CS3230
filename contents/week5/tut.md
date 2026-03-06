{% from "components/pdf.njk" import pdf %}
{% set tutorialNum="tutorial05" %}
{% set title="Tutorial 5" %}

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
