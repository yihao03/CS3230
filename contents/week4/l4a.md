{% from "components/pdf.njk" import pdf %}
{% set title="Lecture 4 part a" %}
{% set file="Lec4a.pdf" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf(file, "lec") }}

## Comparison based algorithms

- Comparison-based algorithms:
  - Elements can only be compared with each other: <, ≤, =, >, ≥
  - No other information of the elements can be used.

{{ pdf(file, "lec", 16) }}
<box type="definition">

<div id="stirling-approximation">

**Stirling's approximation**: For large n, n! can be approximated as:

$$
\log(n!) \approx n \log n - n \log e + O(\log n) \subseteq \Theta(n \log n)
$$

</div>

</box>

## Breaking the barrier: Non-comparison sorts

Counting sort, radix sort, bucket sort etc.  
See assignement for more details
