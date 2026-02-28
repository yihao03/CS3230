{% from "components/pdf.njk" import pdf %}
{% set title="Lecture 1 part b" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf("lec01b.pdf", "lec") }}

## Introduction to Algorithms

### Algorithm paradigms

- Complete Search (for example, using brute force,
  backtracking, branch and bound)
- Divide and Conquer (D&C)
- Dynamic Programming (DP)
- Greedy Algorithm
- Deterministic versus non-deterministic strategies
- Iterative Improvement

### Analyse resource usage

- Time complexity (main focus)
- Space complexity (assume all data fits in memory)

Time-space tradeoff: sometimes we can use more space to reduce time, or vice versa.

#### Modelling Computation: Random Access Machine (RAM)

- count the number of basic instructions needed
- each instruction takes constant time
- Time complextiy based on input size

## Example: Fibonacci numbers

iterative vs. recursive implementation (compare memory usage)

### Recursive implementation

$$
\begin{align*}
Fib(n) &= Fib(n −1)+Fib(n −2) \\
Fib(n) &\ge Fib(n −2)+Fib(n −2) \\
Fib(n) &\ge 2· Fib(n −2) \\
\end{align*}
$$

Between 1 to n, there are $\lceil\frac{n−2}{2}\rceil$ doubling steps
This takes care of odd vs even n cases
Hence $Fib(n) ≥ 2^{\frac{(n−2)}{2}}$

### Iterative implementation

Uses **dynamic programming**

take $O(n)$ time

## Asymptotic analysis

- Measure runtime behaviour for large inputs
- ignore lower order terms and constant multiplicative factors

<box>

**Big O**: Upper bound

> $O(g) = \{f: \exists c > 0 \land n_0 > 0 s.t. \forall n \ge n_0,0 \le f(n) \le c \cdot g(n)\}$

$f \in O(g)$ if $\exists c \gt 0 \land n_0 \ge 0$ such that $0 \le f(n) \le c \cdot g(n)$ for all $n \ge n_0$

</box>

<box>

**Big $\Omega$**: Lower bound  
$f \in \Omega(g)$ if $\exists c \gt 0$ and $n_0 \gt 0$ s.t. $\forall n \ge n_0$: $0 \le c \cdot g(n) \le f(n)$

</box>

<box>

**Big $\Theta$**: Tight bound  
$f \in \Theta(g)$ if $\exists c_1, c_2 > 0$ and $n_0 > 0$ s.t. $\forall n \ge n_0$: $0 \le c_1 \cdot g(n) \le f(n) \le c_2 \cdot g(n)$
</box>

$$
\Theta(g) = O(g) \cap \Omega(g)
$$

<box>

**Little o**: strict upper bound  
$f \in o(g)$ if $\forall c \gt 0, \exists n_0 \gt 0 \text{s.t. } \forall n \ge n_0$: $0 \le f(n) \lt c \cdot g(n)$

basically: $o(g) = O(g) - \Theta(g)$  
e.g. for any given function $f$, $f \in O(f)$ but $f \notin o(f)$

</box>

<box>

**little $\omega$**: strict lower bound  
$f \in \omega(g)$ if $\forall c \gt 0, \exists n_0 \gt 0 \text{s.t. } \forall n \ge n_0$: $0 \le c \cdot g(n) \lt f(n)$

$\omega(g) = \Omega(g) - \Theta(g)$
</box>

## Determining complexity by taking limits

$$
\begin{align*}
&\lim_{n \to \infty} \frac{f(n)}{g(n)} = 0 &\rightarrow f \in o(g) \\
&\lim_{n \to \infty} \frac{f(n)}{g(n)} \lt \infty &\rightarrow f \in O(g) \\
0 \lt &\lim_{n \to \infty} \frac{f(n)}{g(n)} \lt \infty &\rightarrow f \in \Theta(g) \\
&\lim_{n \to \infty} \frac{f(n)}{g(n)} \gt 0 &\rightarrow f \in \Omega(g) \\
&\lim_{n \to \infty} \frac{f(n)}{g(n} = \infty &\rightarrow f \in \omega(g) \\
\end{align*}
$$

<panel header="Proofs" peek>

![little o proof](/assets/o-limit-proof.png)

**Proofs from Tutorial 1**  
<include src="./tut.md#solution"></include>
</panel>
