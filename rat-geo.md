---
documentclass: scrartcl
classoption: DIV=15
title: Geometry with Linear Algebra
subtitle: After [N. J. Wildberger's YouTube lecture series](<https://www.youtube.com/watch?v=8rjxOFAzBa4&index=20&list=PL5A714C94D40392AB> et al)
author: Martin Pitt (<martin@piware.de>)
header-includes: \usepackage[all]{xy}
header-includes: \setcounter{secnumdepth}{2}
...

This builds upon "Projective Geometry" (<http://piware.de/docs/projective-geometry.pdf>)
which defines points, lines, the null conic, the introduction of metrical
structure, the dot product, and perpendicularity.

Definitions
===========

Affine $n$-Point:
:    $A=[a_1,...,a_n]$ with $a_i$ from some field (usually of type $\mathbf{Rat}$)

Projective $n$-Point:
:    $a=[a_1:a_2:...:a_{n+1}]$ (an $n+1$-proportion)

Quadrance between points:
:    $Q(A, B) := (b - a)^2$

One-dimensional affine geometry
===============================
Archimedes' function:
:    ${\mathcal A}(x,y,z):=(x+y+z)^2 - 2(x^2+y^2+z^2) = 4xy - (x+y-z)^2$

Triple Quad(rance) Formula:
:    For three points $A_1$, $A_2$, $A_3$ with $Q_1=Q(A_2,A_3)$,
     $Q_2=Q(A_1,A_3)$, $Q_3=Q(A_1,A_2)$:

     ${\mathcal A}(Q_1,Q_2,Q_3) = 0$, or equivalently $(Q_1+Q_2-Q_3)^2 = 4Q_1Q_2$.

<!--- vim: ft=markdown
-->
