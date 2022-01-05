
# Introduction
The study of Diophantine equations ,the solution of polynomial equationsin integers or rational numbers, has a history.
The term #Diophantine-geometry is of more recent origin and refers to thestudy of Diophantine equations through a combination of techniques from **algebraic
number theory** and **algebraic geometry**.

### Linear

### quadratic equations
$$
aX^2+bXY+cY^2+dX+eY+f=0,\qquad a,\dots,f\in\mathbb{Z},\quad a,b\;or\;c\neq 0
$$
Also called conic sections. By a suitable change of coordinates with rational coefficients, we can transform it into:
$$
\begin{align*}
AX^2+BY^2=C&\qquad ellipse\\
AX^2-Y^2=C&\qquad hyperbola\\
AX+BY^2=C&\qquad parabola
\end{align*}
$$
And e have the following powerful theorem that aids in their
solution.
##### Theorem 0.1 (Hasse–Minkowski) 
Let$f(X,Y)\in Q[X,Y]$be a quadratic polynomial. The equation $f(X, Y)=0$ has a solution $(x, y)\in\mathbb{Q}^2$ if and only if it has a solution $(x, y)\in\mathbb{R}^2$ and a solution $(x, y)\in\mathbb{Q}^2_{p}$ for every prime p. (Here $\mathbb{Q}_{p}$ is the field of p-adic numbers.)

In other words, a quadratic polynomial has a solution in $\mathbb{Q}$ if and only if it has asolution in every **completion** of $\mathbb{Q}$.
Hensel’s lemma says that checking for solutions
in $\mathbb{Q}_{p}$ is more or less the same as checking for solutions in the finite field $\mathbb{Z}/p\mathbb{Z}$, and
this in turn is easily accomplished using #quadratic-reciprocity .

We summarize thesteps that go into the Diophantine analysis of quadratic equations.
1.  Analyze the equations over **finite fields** (quadratic reciprocity);
2. Use this information to study the equations over complete local fields $\mathbb{Q}_{p}$(Hensel’s lemma). (We must also analyze them over R.);
3. Piece together the local information to obtain results for the global field Q (Hasse principle).

The above discussion says that we have a fairly good understanding of the arithmetic of linear and quadratic curves.
The next simplest case, called elliptic curves which given by cubic equations in two variables, is our object of study in this book. The arithmetic of elliptic curves already presents complexities on which much current research is centered.

Briefly, the organization of this book is as follows.
After two introductory chapters giving basic material on algebraic geometry, we start by studying the geometry of elliptic curves over algebraically closed fields (Chapter III).



There are three major exceptions to this general policy:
