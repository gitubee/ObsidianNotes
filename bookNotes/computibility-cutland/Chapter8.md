# Arithmetic and Godel incompleteness theorem
## Formal arithmetic
formalization of #arithmetic: a formal logical language L that is adequate for making statements of ordinary arithmetic of the natural numbers
alphabet: 0, 1, +, x, =,  logical notions $\lnot, \land, \lor, \forall,\exists$ , symbols x,y,z,…, brackets ()
**statements/formulas of L**: meaningful finite sequences of symbols
$\mathscr{S}$ : all statements of L
* divide into true statements: $\mathscr{T}$, and  false statements: $\mathscr{F}$ 

we focus on the true set , so natural questions are:
> (a) Is $\mathscr{T}$  recursive, or even recursively enumerable? 
> (b) Is there a simple-minded subset of  $\mathscr{T}$ (a set of axioms) from which all other statements in $\mathscr{T}$ can be proved?

the answer to both of these questions is **no**

### question A: is $\mathscr{T}$ r.e.?
First, we need to define this problem prisious, by **encoding** the set $\mathscr{T}$ to a set $\mathbb{T}\subseteq \mathbb{N}$, and then we judge $\mathbb{T}$ is a r.e.
standard coding procedure
enumerate all statements: $\{\theta_0,\theta_1,\dots\}$
so the question(a) is 
**Lemma 8.1.2**: Suppose that $M(x_1,…,x_n)$ is a decidable predicate. Then it's possible to construct a statement $\sigma(x_1,…,x_n)\in L$, that for any $a_1,a_2,\dots,a_n\in \mathbb{N}$:
> M(a_1,…,a_n) holds iff σ(a_1,…,a_n )∈T

for each r.e. set A, there is a decidable predicate R(x,y) that:$A=\{x|\;\exists y\;R(x,y)\}$ [Theorem 7.2.4](./Chapter7.md)

then we have: $n\in K\; for\;\exists\ y\sigma_R (n,y)$, then $n\notin K\;for\;\lnot\exists y\sigma_R(n,y)$

**Lemma 8.1.3**: for any n∈N:
* (a) $n\in K\;iff\;\exists\ y\;\sigma_R (n,y)\in T$
* (b) $n\notin K\;iff\;\lnot\exists y\;\sigma_R(n,y)\in T$


**Lemma 8.1.4**: 
* There is a total computable function g such that for all n, $θ_{g(n)}$  is $n\in K$

Proof: use the effictiveness of encoding of $\sigma_R$

**Theorem 8.1.5**:
> $\mathscr{T}$ is not r.e., more $\mathscr{T}$ is productive

Proof: conduct $x\in\overline{K}$ to $g(x)\in\mathbb{T}$


Exercise 8.1.5: 
1. show that $\mathscr{F}$ is productive
## #Incompleteness
### question B
> question B: Is there a simple-minded subset of  $\mathscr{T}$ (a set of axioms) from which all other statements in $\mathscr{T}$ can be proved?

formal system $(\mathscr{A},\mathscr{D})$ for a language L:
* consists of a set $\mathscr{A}\subseteq\mathscr{S}$ 




