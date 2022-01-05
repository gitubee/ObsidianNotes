
# The second Recursion theorem
The first Recursion theorem, together with the Myhill-Shepherdson theorem in the previous chapter, shows that for any #extensional total computable function f there is a number n such that $\phi_{f(n)}=\phi_n$.

The second Recursion theorem says that there is such an n even when f is not extensional: we shall prove this in § 1 of this chapter.

## The second Recursion theorem
##### Theorem 1.1: The second Recursion theorem
Let f be a total unary computable function; then there is a number n such that $\phi_{f(n)}=\phi_{n}$.

Proof: By #s-m-n Theorem there is a total computable function $s(x)$ that for all x:
(*) $\phi_{f(\phi_{x}(x))}(y)\simeq \phi_{s(x)}(y)$
Now take any m such that $s=\phi_{m}$; rewriting (\*) we have:
$$\phi_{f(\phi_{x}(x))}(y)\simeq \phi_{\phi_{m}(x)}(y)$$
Then putting $x=m$ and taking $n=\phi_{m}(m)$(since $\phi_{m}(x)=s(x)$ is total) we have:
$$\phi_{f(n)}(y)\simeq\phi_{n}(y)$$
as required.

Corollary 1.2
If f is a total computable function, there is a number n such that $W_{f(n)}=W_n$ and $E_{f(n)}=E_{n}$.

Corollary 1.3
If f is a total computable function there are arbitrarily large 
numbers n such that $\phi_{f(n)}=\phi_{n}$.

Corollary 1.4
Let $f(x,y)$ be any computable function; then there is an index e 
such that $\phi_{e}(y)\simeq f(e,y)$.

Proof: Use s-m-n theorem to get a total computable function $s$ such that $\phi_{s(x)}\simeq f(x,y)$. 

###### Example 1.5
1. There is a number n such that $\phi_{n}(x)=x^{n}$.
2. There is a number n such that $W_{n}=\{n\}$.

##### Theorem 1.6: Rice Theorem
Suppose that $\emptyset\subset\mathscr{A}\subset\mathscr{C}_1$, and let $A=\{x:\phi_x\in\mathscr{A}\}$. Then A is not recursive.
Proof: Let $a\in A$ and $b\notin A$, if A is recursive, then the function f given by:
$$
f(x)=\bigg\{\begin{array}{ll}a&if\;x\notin A\\b&if\;x\in A\\\end{array}
$$
is computable. Then we have $x\in A\Leftrightarrow f(x)\notin A$.

##### Theorem 1.7
Suppose that f is a total increasing function such that:
(a) if $m\neq n$, then $\phi_{f(m)}\neq \phi_{f(n)}$;
(b) $f(n)$ is the least index of the function $\phi_{f(n)}$.
Then f is not computable.

Applications of the second Recursion theorem such as the following can be interpreted in anthropomorphic terms.
Let P be a program. We can regard the code number $\gamma(P)$ as a description of P.We could regard the program P as capable of self-reproduction if for all inputs x the computation P(x) gave as output its own description $\gamma(P)$.

##### Theorem 1.8
There is a program P such that for all x, $P(x)\downarrow\gamma(P)$; i.e. P is self-reproducing.

###### Exercises 1.10
1. Show that there is a number n such that: 
	$\phi_{n}(x)=[\sqrt[n]{x}]$;
	$W_n=E_n=n\mathbb{N}$;
3. Show that there is a number n such that $\phi_{e}(x)=e^2$ for all x;
4. Is there a number n such that $W_{n}=\{x:\phi_{n}(x)\uparrow\}$;
5. Suppose that $\mathscr{A}\subseteq\mathscr{C}_1$, and let $A=\{x:x\in\mathscr{A}\}$, show that $A\nleq_m\overline{A}$;
6. Give an example of a total computable function f such that: 
	(i) if $\phi_{x}$ is total, then so is $\phi_{f(x)}$;
	(ii) there is no fixed point n for f with $\phi_{n}$ total.
7. Prove the second Recursion theorem for k-ary computable 
functions: if f is a total computable function there is a number n 
such that $\phi^{(k)}_{f(n)}=\phi^{(k)}_{n}$;
8. Show that theorem 1.1 may be improved to: For any total 
computable function f, there is an increasing recursive function $n(t)$ such that for every t, $\phi_{n(t)}=\phi_{f(n(t))}$.
9. Prove that the second Recursion theorem does not depend on 
the particular effective numbering of programs that is chosen.

## Discussion
It is essentially a simple diagonal argument applied to effective enumerations of computable functions.
Suppose that h is a computable function. If h is total, then the 
enumeration E given by:
$E:\phi_{h(0)},\phi_{h(1)},\phi_{h(0)}\dots$
is an effective enumeration of computable functions.
If h is not total, we can still regard h as enumerating a sequence of computable functions E by setting:
$$\phi_{h(x)}(y)\simeq \psi_{U}(h(x),y)=\bigg\{
\begin{array}{ll}\phi_{h(x)}(y)&if\;h(x)\;is\;defined\\
undefined&if\;h(x)\;is\;undefined\end{array}
$$
###### Lemma 2.1
Suppose that h is a computable function. There is a total computable function $h'$ such that h and $h'$ enumerate the same sequence of computable functions.


