{% from "components/pdf.njk" import pdf %}
{% set title="Proof of Correctness" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

## Iterative version

{{ pdf("Lec3a.pdf", "lec", 7) }}

For a proof: important to also consider elements not being acted on in a step (e.g. state that it stays the same)

- Initialization: $n=1$, trivially/vacuously true?
- Maintenance: if $n-1$ holds, n is true
- Termination: imagine there's a $k+1^{th}$ step, nothing changes

{{ pdf("Lec3a.pdf", "lec", 17) }}

## Recursive version

- Base case
- Inductive step

{{ pdf("Lec3a.pdf", "lec", 43) }}
