# Effective operations on partial functions

we have studied effectively computable operations on **numbers** it is natural to ask whether there is a comparable notion for operations on **functions**.

In § 1 of this chapter we discuss the features we might reasonably expect of an effective operator on partial functions: this leads to the formulation of the definition of **recursive operators** on partial 
functions.
## Recursive operators

$\mathscr{F}_{n}$:  the class of all partial functions from $\mathbb{N}^{n}$ to $\mathbb{N}$. 
#operator:  a function $\varPhi$: $\mathscr{F}_{n}\rightarrow\mathscr{F}_{m}$
We focus on totally defined operators, which domain is the whole of $\mathscr{F}_{n}$.
The chief problem is that both an 'input' function and the 'output' function are infinite objects, and hence incapable of being given in a finite time. 

To see how this problem can be overcome, consider the following 
operators from $\mathscr{F}_{1}$ to $\mathscr{F}_{1}$:
* $\varPhi_1(f)=2f$;
* $\varPhi_2(f)=g$, where $g(x)=\sum_{y\leq x}f(y)$
Intuitively we might regard them as effective operators, because any defined value of the output function can be effectively calculated in a finite time using only a finite part of the input function f.

We say that $\theta$ is a finite function if its domain is a finite set. And we use:
> $\theta$ always denotes a finite function in this chapter. 

We make this precise by coding each finite function $\theta$ by a number $\overline{\theta}$ and using ordinary computability.

##### Definition 1.1: #recursive-operator
Let $\varPhi:\mathscr{F}_{m}\rightarrow \mathscr{F}_{n}$ Then is a recursive operator if there is a computable function $\phi(z,x)$ such that for all $f\in\mathscr{F}_{m}$ and $x\in\mathbb{N}^{n}$, $y\in\mathbb{N}$:
$\varPhi(f)(\textbf{x})\simeq y$ iff there is finite $\theta\subseteq f$ such that $\phi(\widetilde{\theta},\textbf{x})\simeq y$.

An important feature of recursive operators is that they are **continuous** and **monotone** in the following sense. 

##### Definition 1.3: #continuous and #monotone
Let $\varPhi:\mathscr{F}_m\rightarrow \mathscr{F}_n$ be an operator.
1. $\varPhi$ is continuous if for any $f\in\mathscr{F}_m$ and all $\textbf{x},y$:
	$\varPhi(f)(\textbf{x})\simeq y$ iff there is finite $\theta\subseteq f$ with $\varPhi(\theta)(\textbf{x})\simeq y$;
2. $\varPhi$ is monotone if whenever $f,g\in\mathscr{F}_m$ with $f\subseteq g$ then $\varPhi(f)\subseteq\varPhi(g)$.

#question <span style="font-style:oblique;color:red">continous is obvious? and what's the meaning of it? </span>


It's important to prove following theorem logically, by understanding the function operator.

##### Theorem 1.4
A recursive operator is #continuous and #monotone.

Proof: For continuity, Let $\varPhi$ be a recursive operator, and $\phi$ is the computable function. 
For monotonicity, 

#question <span style="font-style:oblique;color:red">Is an continous operator must be monotone? If yes, prove it, if not, find a  instance. And reversely?</span>
#question <span style="font-style:oblique;color:red">Find a operator which is continuous and monotone, but not recursive.</span>
continuity property l.3(1) specifies that a value $\varPhi(f)(\textbf{x})$ is determined (if at all) by a finite amount of **positive information** about f.  **Negative information** that would indicate points where f is not defined.

The **positive information topology** on $\mathscr{F}_m$ is defined by taking as base of open neighbourhoods sets of the form:
$$
U_{\theta}=\{f:\theta\subseteq f\}
$$

##### Theorem 1.5
Let $\varPhi:\mathscr{F}_m\rightarrow\mathscr{F}_n$ be an operator. Then $\varPhi$ is a recursive operator iff:
(a) $\varPhi$ is continuous;
(b) the function $\phi(z,\textbf{x})$ given by:
$$
\bigg\{\begin{array}{ll}
\phi(\widetilde{\theta},\textbf{x})\simeq \varPhi(\theta)(\textbf{x})& for\;\theta\in\mathscr{F}_m\\
\phi(\widetilde{\theta},\textbf{x})\;is\;undefined&for\;all\;other\;z\\
\end{array}\;is\;computable
$$

Proof: Support  that $\varPhi$ is recursive with computable function $\phi_1$ such that:
$\varPhi(f)(\textbf{x})\simeq y$ iff $\exists\theta(\theta\subseteq f\;and\;\phi_1(\widetilde{\theta},\textbf{x})\simeq y)$
Then we have:
$\phi(\widetilde{\theta},\textbf{x})\simeq y\Leftrightarrow \exists\theta_1(\theta_1\subseteq \theta\;and\;\phi_1(\widetilde{\theta}_1,\textbf{x})\simeq y)$
Conversely, suppose that conditions (a) and (b) of the theorem hold:
$$
\begin{array}{rl}
\varPhi(f)(\textbf{x})\simeq y&\Leftrightarrow \exists\theta(\theta\subseteq f\;and\;\varPhi(\theta,\textbf{x})\simeq y)(by(a))\\
&\Leftrightarrow\exists\theta(\theta\subseteq f\;and\;\phi(\widetilde{\theta},\textbf{x})\simeq y)(by(b))
\end{array}
$$

This theorem enables us to show quite easily that the following 
operators are all recursive: 
###### Examples 1.6
1. (The diagonalisation operator) $\varPhi(f)(x)\simeq f(x,x),(f\in\mathscr{F}_2)$;
2. $\varPhi(f)(x)\sum_{y\leq x}f(y),(f\in\mathscr{F}_1)$;
3. Let $g\in\mathscr{F}_1$ be computable. Define $\varPhi:\mathscr{F}_n\rightarrow\mathscr{F}_n$ by $\varPhi(f)=g\circ f$;
4. (The Ackermann operator): Let $\varPhi:\mathscr{F}_2\rightarrow\mathscr{F}_2$ be given by:
	$\varPhi(f)(0,y)=y+1$, $\varPhi(f)(x+1,0)\simeq f(x,1)$, $\varPhi(f)(x+1,y+1)\simeq f(x,f(x+1,y))$
5. (The $\mu$-operator): Consider $\varPhi:\mathscr{F}_{n+1}\rightarrow\mathscr{F}_{n}$ given by $\varPhi(f)(\textbf{x})\simeq \mu y(f(\textbf{x},y)=0)$;

#question <span style="font-style:oblique;color:red">$\mu$-operator is recursive? if $f(x)=\textbf{0}$, we use $\theta(0)=0$ and $\theta(1)=0$, we get different value in $\mu y$?</span>
#answer <span style="font-style:oblique;color:red">If function have undefined value on $x_i$, then $\mu y$ will under $x_i$ or undefined</span>

**recursive functional**: a recursive operator like $\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{0}$; But for $\mathscr{F}_0$, we need something to define undefined constant, so $\mathscr{F}_0=\mathbb{N}\cup\{\omega\}$.

##### Definition : #recursive-functional
An operator $\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{0}$ is a recurisive functional if there is a computable function $\phi(x)$ such that for any $f\in \mathscr{F}_{m}$ and $y\in \mathbb{N}$:
> $\varPhi(f)\simeq y$ iff $\exists\theta(\theta\subseteq f\;and\;\phi(\widetilde{\theta})\simeq y)$
> And $\varPhi(f)\simeq \omega$ if $\varPhi(f)$ is undefined.

###### Exercises 1.7
1. Show that the following operators are recursive:
	(a) $\varPhi(f)=f^2$;
	(b) $\varPhi(f)=g$ where $g\in\mathscr{F}_1$ is fixed and computable;
	(c) $\varPhi(f)=f\circ g(f\in\mathscr{F}_1)$ where $g\in \mathscr{F}_n$ is fixed computable;
	(d) Let $h\in\mathscr{F}_{n+1}$ be a fixed computable function, define $\varPhi:\mathscr{F}_{n+1}\rightarrow\mathscr{F}_{n+1}$ by:
2. Prove that if $varPhi$ is a recursive operator and f is computable then so is $\varPhi(f)$.
3. Deccide whether the following operators $\varPhi:\mathscr{F}_{1}\rightarrow\mathscr{F}_{1}$ are (i) monotonic, (ii) continuous, (iii) recursive. 
	$$
	(a)\;\varPhi(f)(x)\simeq\bigg\{\begin{array}{ll}
	f(x)&if\;Dom(f)\;is\;finite\\
	undefined&if\;Dom(f)\;is\;infinite
	\end{array}
	$$
	$$
	(b)\;\varPhi(f)(x)\simeq\bigg\{\begin{array}{ll}
	0&if\;f\;is\;defined\\
	undefined&otherwise
	\end{array}
	$$
	$$
	(c)\;\varPhi(f)(x)\simeq\bigg\{\begin{array}{ll}
	0&if\;f(x)\in K\;and\;f(x)\;is\;defined\\
	1&if\;f(x)\notin K\;and\;f(x)\;is\;defined\\
	undefined
	\end{array}
	$$
	$$
	(d)\;\varPhi(f)(x)\simeq\bigg\{\begin{array}{ll}
	undefined&if\;Dom(f)\;is\;finite\\
	f(x)&if\;Dom(f)\;is\;infinite
	\end{array}
	$$
4. Suppose that $\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{n}$ and $\varPsi:\mathscr{F}_{n}\rightarrow\mathscr{F}_{p}$ are recursive operators. Prove that $\varPsi\circ\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{p}$ is recursive. 
5. 
7. Suppose that $\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{n}$ and $\varPsi:\mathscr{F}_{n}\rightarrow\mathscr{F}_{p}$ are continuous operators. Prove that $\varPsi\circ\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{p}$ is continuous. 


Proof: For 3, (a) is not continuous nor monotonic, beacuse for function f which Dom(f) is infinite, it's finite restriction $\theta$, $\varPhi(\theta)\neq undefined$; (b) is recursive, (c) is continuous and monotonic, but not recursive, because we can't find a computable function $\Phi$; (d) is nor too.
For 4, suppose that $\varPhi,\phi$ and $\varPsi,\psi$, we construct $\phi(\widetilde{\theta},x)=\psi(\widetilde{\theta_1},x)*\exists\theta_{1}(\forall (y,f(y))\in\theta_{1}(\phi(\widetilde{\theta},y)==f(y)))$

## Effective operations on computable functions

In chapter 5 § 3 we considered that certain operations on 
computable functions should be called effective because they can be given by total computable functions acting on indices.
We shall see in this section that any recursive operator $\varPhi$, when restricted to computable functions, yields an effective operation of this kind on indices.
Myhill and Shepherdson proved all such operations on indices of computable functions arise in this way. 
Two parts of the Myhill-Shepherdson, first the easier part.
##### Theorem (Myhill-Shepherdson, part I)
Suppose that $\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{n}$ is a recursive operator. Then there is a total computable function h such that:
> $\varPsi(\phi^{(m)}_e)=\phi^{(n)}_{h(e)}\qquad (e\in\mathbb{N})$

##### Definition 2.2: #extensional
A total function $h:\mathbb{N}\rightarrow\mathbb{N}$ is extensional if for all a, b, if $\phi_a=\phi_b$ then $\phi_{h(a)}=\phi_{h(b)}$.

##### Theorem 2.3:  (Myhill-Shepherdson, part II) 
Suppose that h is an extensional total computable function. Then there is a unique recursive operator $\varPsi$ such that $\varPsi(\phi_{e})=\phi_{h(e)}$ for all e. 

Proof: By h is an extensional total computable function, then h defines an operator $\varPsi_0:\mathscr{C}_1\rightarrow\mathscr{C}_1$ by: $\varPsi_{0}(\phi_e)=\phi_{h(e)}$. Then we need a unique recursive operator $\varPsi: \mathscr{F}_1\rightarrow\mathscr{F}_1$ that extends $\varPsi_0$ and be continuous, must be defined by:
> 

The proof are four parts:
1. $\varPsi_0$ is continuous;
2. The above definition dinfines an operator $\varPsi$;
3. $varPsi$ extends $varPsi_0$;
4. $\varPsi$ is recursive;

Remarks:
1. The proof of theorem 2.3 actually shows that for any extensional 
computable h there is a unique continuous operator $\varPsi: \mathscr{F}_1\rightarrow\mathscr{F}_1$ such that $\varPsi(\phi_{e})=\phi_{h(e)}$ all e, and that this operator is recursive.

##### Exercises 2.6


## The first Recursion theorem
The first Recursion theorem of Kleene is a #fixed-point theorem for recursive operators, and is often referred to as the Fixed point 
theorem of recursion theory.
##### The first Recursion theorem (Kleene)
Suppose that $\varPhi:\mathscr{F}_{m}\rightarrow\mathscr{F}_{n}$ is a recursive operator. Then there is a computable function $f_{\varPhi}$ that is the least fixed point of $\varPhi$; i.e.:
(a) $\varPhi(f_{\varPhi})=f_{\varPhi}$;
(b) if $\varPhi(g)=g$, then $f_{varPhi}\subseteq g$.
Hence, if $f_{\varPhi}$ is total, its the only fixed point of $\varPhi$.

Proof: We use the continuity and monotonicity of $\varPhi$ to construct the least fixed point $f_{\varPhi}$ as follows. Define a sequence of functions $\{f_n\}(n\in\mathbb{N})$ by:
> $f_0=f_{\emptyset}$, $f_{n+1}=\varPhi(f_n)$

Then $f_{0}=f_{\emptyset}\subseteq f_1$, and if $f_{n}\subseteq f_{n+1}$, by monotonicity we have that $f_{n+1}=\varPhi(f_n)\subseteq\varPhi(f_{n+1})=f_{n+2}$. Hence $f_{n}\subseteq f_{n+1}$ for all n. 
Now let :
> $f_{\varPhi}=\bigcup_{n\in\mathbb{N}}f_{n}$
> $\Leftrightarrow f_{\varPhi(\textbf{x})}\simeq y$ iff $\exists n$ such that $f_{n}(x)\simeq y$

We shall show that $f_{\varPhi}$ is a fixed point for $\varPhi$.

Remark. The recursiveness of the operator $\varPhi$ was used in this proof only in showing that $f_{\varPhi}$ is computable. The first part of the proof shows that any continuous operator has a least fixed point. 

In the following examples, a recursive operator may have many fixed points, and the least fixed point is not necessarily a 
total function. 

###### Examples 3.2
1. Let $\varPhi$ be the recursive operator given by:
	$\varPhi(f)(0)=1$, $\varPhi(f)(x+1)\simeq f(x+2)$
Then the least fixed points is 
2. Recall the definition of the Ackermann function $\psi$ in [[Chapter2#Examples 5.5|EG2-5.5(c)]].
	The first Recursion theorem gives a neat proof that these equations do define a unique function $\psi$ and that $\psi$ is total and computable. 
	Let $\varPhi$ be the Ackermann operator given in [[#Examples 1 6|EG10-1.6(4)]]. The fixed points of $\varPhi$ are the functions that satisfy the above equations. Let $\psi=f_{varPhi}$, then $\psi$ is a computable function satisfying these equations, so we have only to show that $\psi$ is total.
	
	
	
We were able to see quite easily in chapter 2 that primitive recursive definitions are meaningful, but with more complex recursive definitions this is not so obvious; conceivably there are no functions satisfying the proposed definition. This is where the first Recursion theorem comes in.
Very general kinds of definition by recursion are represented by an 
equation of the form
> (3.3) $f=\varPhi(f)$

###### Exercises 3.4
1. Find the least fixed points of the following operators:
	(a) $\varPhi(f)=f$;
	$$(b)\qquad\varPhi(f)(x)=\bigg\{
	\begin{array}{ll}
	0&if\;x=0(f\in\mathscr{F}_1)\\
	2x-1+f(x-1)&if\;x>0
	\end{array}$$
	$$(c)\qquad\varPhi(f)(x,y)=\bigg\{
	\begin{array}{ll}
	0&if\;x=0\\
	f(x-1,f(x,y))&if\;x>0
	\end{array}$$
2. (McCarthy) Show that the function m(x) given by:
	$$
	m(x)=\bigg\{\begin{array}{ll}
	91&ifx\leq 100\\
	x-10&otherwise
	\end{array}
	$$
	is only fixed point of the recursive operator $\varPhi$ given by:
	$$
	\varPhi(f)(x)=\bigg\{\begin{array}{ll}
	f(f(x+11))&if\;x\leq 100\\
	x-10&otherwise
	\end{array}
	$$
## An application to the semantics of programming languages

We shall see in this section how the first Recursion theorem helps to resolve a problem in the semantics of computer programming languages - the area that deals with the question of giving meaning to programs.