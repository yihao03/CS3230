{% from "components/pdf.njk" import pdf %}
{% macro snippet(file) %}
{% set parts = file.split('#') %}
{% set filepath = parts[0] %}
{% set heading = parts[1] | replace('-', ' ') | title if parts[1] else '' %}

# {{heading}}

<include src={{file}}></include>

---

{% endmacro %}

## Useful facts

{{ pdf("Asymptotic_Analysis-Useful-Facts.pdf", "")}}
_when rearranging terms to proof inequality, it is helpful to group terms together and put on each site of the equation_

---

## Probability revision

{{ pdf("prob-revision.pdf", "")}}

---

{{ snippet("./week4/l4b.md#average-case-analysis") }}
{{ snippet("./week5/l5.md#principle-of-deferred-decision") }}
{{ snippet("./week5/l5.md#union-bound") }}
{{ snippet("./week5/l5.md#markov-inequality") }}

# Useful equations

$$
1+x \le e^x \quad \text{for all } x \in \mathbb{R}
$$

## Harmonic series

$$
H_n = \sum_{k=1}^{n} \frac{1}{k} = \frac{1}{1} + \frac{1}{2} + \cdots + \frac{1}{n} \approx \ln n + \gamma
$$

where $\gamma \approx 0.577$ is Euler's constant.

## Geometric series

For $r \neq 1$:

$$
\sum_{k=0}^{n} r^k = \frac{r^{n+1} - 1}{r - 1} = \frac{1 - r^{n+1}}{1 - r}
$$

If $|r| < 1$:

$$
\sum_{k=0}^{\infty} r^k = \frac{1}{1 - r}
$$

## Arithmetic series

$$
\sum_{k=1}^{n} k = \frac{n(n+1)}{2}
$$

## Sum of squares

$$
\sum_{k=1}^{n} k^2 = \frac{n(n+1)(2n+1)}{6}
$$

## Sum of cubes

$$
\sum_{k=1}^{n} k^3 = \left(\frac{n(n+1)}{2}\right)^2
$$

## Stirling's approximation

<include src="./week4/l4a.md#stirling-approximation"></include>

More precisely:

$$
n! = \sqrt{2\pi n} \left(\frac{n}{e}\right)^n \left(1 + \Theta\left(\frac{1}{n}\right)\right)
$$

## Binomial theorem

$$
(x + y)^n = \sum_{k=0}^{n} \binom{n}{k} x^k y^{n-k}
$$

## Expected value

$$
E[X] = \sum_{x} x \cdot Pr[X=x]
$$

## Linearity of expectation

$$X = A + B \implies \mathbb{E}[X] = \mathbb{E}[A] + \mathbb{E}[B]$$
More generally, if $X = \sum_{i=1}^{n} X_i$, then:

$$
\mathbb{E}[X] = \sum_{i=1}^{n} \mathbb{E}[X_i]
$$

## Indicator random variables

Let $\varepsilon$ be an event. The indicator random variable $\mathbf{1}_{\varepsilon}$ for $\varepsilon$ is defined as:

$$\mathbf{1}_{\varepsilon} = \begin{cases} 1 & \text{if } \varepsilon \text{ occurs} \\ 0 & \text{otherwise} \end{cases}$$

**Observation:** $\mathbb{E}[\mathbf{1}_{\varepsilon}] = \Pr[\varepsilon]$
