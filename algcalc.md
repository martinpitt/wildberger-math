---
documentclass: scrartcl
classoption: DIV=15
title: Algebraic Calculus
subtitle: After [N. J. Wildberger's YouTube lecture series](<https://www.youtube.com/watch?v=rTw6XbmO8Nc&list=PLzdiPTrEWyz4rKFN541wFKvKPSg5Ea6XB>)
author: Martin Pitt (<martin@piware.de>)
header-includes: \setcounter{secnumdepth}{2}
...

\newcommand{\cll}{<\!\![}
\newcommand{\clr}{]\!\!>}
\newcommand{\csl}{<\!\!\{}
\newcommand{\csr}{\}\!\!>}
\newcommand{\pascal}{\mathbf{P}}

Notation
========
Data structures:

repetition   ordered                    cyclic                        unordered
----------   -------                    ------                        --------
yes          list $[1, 1, 2, 4]$        c-list $\cll 1, 1, 2, 4\clr$  multi-set $[1~1~2~4]$
no           ordered set $\{1, 2, 4\}$  c-set  $\csl 1, 2, 4\csr$     set $\{1~2~4\}$

Basic Definitions
=================

(Affine) Point
:    $A:=[x,y]$ -- pair of rational numbers

Midpoint of two points
:    The midpoint of $[r, s]$ and $[t, u]$ is $[\frac{r+t}{2}, \frac{s+u}{2}]$.

Line
:    linear equation in the variables $x$ and/or $y$, of the form $ax+by=c$

Side
:    $\overline{AB}:=\{A~B\}$ -- set of two points

Oriented side
:    $\widetilde{AB}:=\{A,B\}$ -- ordered set of two points

Triangle
:    $\overline{ABC}:=\{A~B~C\}$  -- set of three points, with three sides
     (two-element subsets)

Oriented Triangle
:    $\widetilde{ABC}:=\csl A,B,C\csr$ -- cyclically ordered set of three points

Basic Relations
===============

Incidence
:   The point $[x_0,y_0]$ is incident with the line $ax+by=c \Leftrightarrow ax_0 + by_0 = c$

Parallelism
:   The lines $l: ax+by=c$ and $h: dx+ey=f$ are parallel  $\Leftrightarrow ae-bd=0$

Basic concepts of area
======================

 * Defining area in terms of sums of rectangles is not ideal (additive?
   rotationally invariant? can parts overlap or cancel?)

 * Area is at heart a concept of affine geometry: relative area between a shape
   (possibly approximated by subdivisions of the basic parallelograms) and the
   basic parallelogram

 * Signed area of the oriented triangle $\widetilde{OAB}$ with $A=[x_a,y_a]$ and $B=[x_b,y_b]$:

    $s(\widetilde{OAB}):=\frac{1}{2}(x_ay_b - y_ax_b) = \frac{1}{2}\begin{vmatrix} x_a & x_b \\ y_a & y_b \end{vmatrix}$

 * Signed area of an oriented side: $s(\widetilde{AB}):=s(\widetilde{OAB})$
   \qquad $s(\widetilde{AB}) = -s(\widetilde{BA})$

\clearpage

The cross product
=================

**Definition**: If $\vec{u} = (x_u, y_u)$ and $\vec{v} = (x_v, y_v)$ are vectors, then
$\vec{u}\times\vec{v}:= x_uy_v - y_ux_v = \begin{vmatrix} x_u & x_v \\ y_u & y_v \end{vmatrix}$

**Properties:**

 * $\vec{u}\times(\vec{v}+\vec{w}) = \vec{u}\times\vec{v} + \vec{u}\times\vec{w}$ \qquad (distributive)
 * $(\vec{u}+\vec{v})\times\vec{w} = \vec{u}\times\vec{w} + \vec{v}\times\vec{w}$ \qquad (distributive)
 * $(\lambda\vec{u})\times\vec{v} = \lambda(\vec{u}\times\vec{v}) = \vec{u}\times(\lambda\vec{v})$
   \qquad (linear)
 * $\vec{u}\times\vec{v} = - \vec{v}\times\vec{u}$ (skew-symmetric)
 * $\vec{u}\times\vec{u} = 0$

With that, $s(\widetilde{OAB}) = \frac{1}{2}\vec{OA}\times\vec{OB}$.

Area of polygons
================

Triangle cross product theorem:
:   For any oriented triange $\widetilde{ABC}$:
    $\vec{AB}\times\vec{AC} = \vec{BC}\times\vec{BA} = \vec{CA}\times\vec{CB}$

Signed area of a general triangle:
:    $s(\widetilde{ABC}):=\frac{1}{2}\vec{AB}\times\vec{AC} = \frac{1}{2}\vec{BC}\times\vec{BA} = \frac{1}{2}\vec{CA}\times\vec{CB}$

     $= s(\widetilde{AB}) + s(\widetilde{BC}) + s(\widetilde{CA})$

Signed area of an n-gon:

:    $s(\widetilde{A_1 A_2 … A_n}) = s(\widetilde{A_1 A_2}) + s(\widetilde{A_2 A_3}) + … +s(\widetilde{A_n A_1})$ \quad (Meister's formula)

Oriented Polygonal Splines (OPS)
================================

More general objects than oriented n-gons: repetition of points is allowed,
closure is not necessary.

**Definitions**:

 * An OPS is a list of affine points: $\gamma = \overrightarrow{A_1 A_2 ... A_n} := [A_1, A_2, ..., A_n]$.
 * Begin point $b(\gamma) := A_1$, end point $e(\gamma) := A_n$.
 * $\gamma$ is closed $\Leftrightarrow b(\gamma) = e(\gamma)$
 * An oriented edge is an OPS of the form $\overrightarrow{A_1 A_2}$.
 * A cyclic OPS (COPS) is a cyclic list of affine points:
   $\delta = \overleftrightarrow{A_1 A_2 ... A_n} := \cll A_1, A_2, ..., A_n\clr$.

**Signed area**:

 * If $A=[x_a, y_a]$ and $B=[x_b, y_b]$ are points, then
   $s(\overrightarrow{AB}) := \frac{x_a y_b - y_a x_b}{2}$.
 * $s(\gamma) := s(\overrightarrow{A_1 A_2}) + s(\overrightarrow{A_2 A_3}) + ... + s(\overrightarrow{A_{n-1} A_n})$
 * $s(\delta) := s(\overrightarrow{A_1 A_2}) + s(\overrightarrow{A_2 A_3}) + ... + s(\overrightarrow{A_{n-1} A_n}) + s(\overrightarrow{A_n A_1})$

Area of parabolic splines
=========================

If $A_k:=[k,k^2]$, the signed area of the parabolic OPS:

$\displaystyle s(\overrightarrow{A_0 A_1 ... A_n})=\sum_{k-1}^n \frac{k(k-1)}{2}=\frac{(n-1)n(n+1)}{6}$


When subdividing the interval $[0, 1]$ with $B_k:=[\frac{k}{n}, (\frac{k}{n})^2]$:

$\displaystyle s(\overrightarrow{B_0 B_1 ... B_n}) = \frac{1}{n^3}s(\overrightarrow{A_0 A_1 ... A_n}) = \frac{1}{6}(1-\frac{1}{n^2})$

As $n$ gets big, this approaches $\frac{1}{6}$.

Faulhaber's Formulas and Bernoulli Numbers
==========================================

$\displaystyle S_k(n) := \sum_{i=1}^n i^k$ \qquad
$S_1(n) = \frac{n(n+1)}{2}$, $S_2(n) = \frac{n(n+1)(2n+1)}{6}$, $S_3(n)=\frac{n^2(n+1)^2}{4}$

Historical approach (Bernoulli)
-------------------------------

Pascal matrix $\pascal$: $a_{i,j} := {i \choose j} = \frac{i!}{j!(i-j)!} = \scriptsize\begin{pmatrix} 1 & 0 & 0 & 0 \\ 1 & 1 & 0 & 0 \\ 1 & 2 & 1 & 0 \\ 1 & 3 & 3 & 1 \end{pmatrix}$ (indexed from zero)

Columns of $\pascal$ can be summed easily: $\displaystyle \sum_{i=0}^n{i\choose j} = {n+1 \choose j+1}$

Express pure powers of $i$ in terms of $S_k(n)$:
   $\displaystyle S_k(n)=\frac{1}{k+1}\sum_{j=0}^k (-1)^j {k+1 \choose j}B_j n^{k+1-j}$

where $B_j$ are \emph{Bernoulli numbers}.

Approach with Linear Algebra
----------------------------

Telescoping series: for $k\ge 1$, $\displaystyle \sum_{m=1}^n \left(m^k - (m-1)^k \right) = n^k$

By the binomial theorem: $\displaystyle m^k-(m-1)^k = \sum_{i=1}^k (-1)^{i+1}{k\choose i}m^{k-i}$

E. g. for $k=4$: $\displaystyle \sum_{m=1}^n(4m^3 - 6m^2 + 4m - 1) = 4S_3(n) - 6S_2(n) + 4 S_1 - S_0 = n^4$

Matrix form for $k\le 4$:
$\scriptsize \underbrace{\begin{pmatrix} 1 & 0 & 0 & 0 \\ -1 & 2 & 0 & 0 \\ 1 & -3 & 3 & 0 \\ -1 & 4 & -6 & 4\end{pmatrix} }_{Q} \begin{pmatrix} S_0(n)\\ S_1(n) \\ S_2(n) \\ S_3(n)\end{pmatrix} = \begin{pmatrix}n^1 \\ n^2 \\ n^3 \\ n^4\end{pmatrix}$

Invert and solve for the $n^k$. First column of the inverted matrix are the
Bernoulli numbers.

$\pascal$ a conjugates: $\pascal = D\cdot E \cdot D^{-1}$ with
$D=(d_{i,i}=i!)=\scriptsize\begin{pmatrix}1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 2 & 0 \\ 0 & 0 & 0 & 6\end{pmatrix}$
and
$E=\scriptsize\begin{pmatrix} 1 & 0 & 0 & 0 \\ 1 & 1 & 0 & 0 \\ \frac{1}{2} & 1 & 1 & 0 \\ \frac{1}{6} & \frac{1}{2} & 1 & 1\end{pmatrix}$

$E$ can be written in terms of the standard lower shift matrix $L$ with $L_{i,j}=\delta_{i,j+1}$:

$E=I + L + \frac{1}{2}L^2 + \frac{1}{6}L^3$, or more generally,
$\displaystyle E_n=\sum_{i=0}^n \frac{1}{i!} L_n^i$

Thus $\pascal$ can be inverted efficiently with $\pascal^{-1}=D\cdot E^{-1} \cdot D^{-1}$.
$D^{-1}$ is trival (diagonal matrix), and with the decomposition into $L$,
$E^{-1}$ can be calculated as a polynom and $L_n^n = 0$.

Similarly, $Q$ factorizes: $Q = \widetilde{D}\cdot B\cdot D^{-1}$ with
$\widetilde{D}=(d_{i,i}=(i+1)!)$ (starting with 1! instead of 0!) and
$B_4=\scriptsize\begin{pmatrix} 1 & 0 & 0 & 0 \\ -\frac{1}{2} & 1 & 0 & 0 \\ \frac{1}{6} & -\frac{1}{2} & 1 & 0 \\ -\frac{1}{24} & \frac{1}{6} & -\frac{1}{2} & 1 \end{pmatrix}$ or more generally,
$\displaystyle B_n=\sum_{i=0}^n (-1)^i \frac{1}{(i+1)!} L_n^i$.

