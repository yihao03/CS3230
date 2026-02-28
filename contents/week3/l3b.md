{% from "components/pdf.njk" import pdf %}
{% set title="Divide and Conquer" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf("Lec3b.pdf", "lec") }}

e.g. Merge sort

1. Divide the problem into smaller subproblems.
1. consider splitting and combining cost
1. Solve the subproblems recursively.
1. Combine the subproblem solutions to get the solution of the full problem.

# Reformulate to break problem into subproblems

Allow divide and conquer method to be applied to a wider range of problems.  
e.g. using clever ways to reduce the number of subproblems, or to reduce the cost of splitting and combining.

## Reducing number of subproblems

{{ pdf("Lec3b.pdf", "lec", 27) }}
