{% from "components/pdf.njk" import pdf %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf(file, "lec") }}
