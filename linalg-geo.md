---
documentclass: scrartcl
classoption: DIV=15
title: Geometry with Linear Algebra
subtitle: After [N. J. Wildberger's YouTube lecture series](<https://www.youtube.com/watch?v=nJdWFoliRnc&list=PL01A21B9E302D50C1&index=27>)
author: Martin Pitt (<martin@piware.de>)
header-includes: \usepackage[all]{xy}
header-includes: \setcounter{secnumdepth}{2}
...

This builds upon "Projective Geometry" (<http://piware.de/docs/projective-geometry.pdf>)
which defines points, lines, the null conic, the introduction of metrical
structure, the dot product, and perpendicularity.

Definitions
===========

Quadrance
:    Measures the separation of two points, or the size of a vector.
     $Q(\vec{a}) := \vec{a}\cdot\vec{a}$

Perpendicularity
:    Two vectors are perpendicular $\Leftrightarrow \vec{a}\cdot\vec{b}=0$

Isometry
:    A linear transformation $T:\mathbb{V}^n \rightarrow \mathbb{V}^n$ is an
     isometry $\Leftrightarrow T(\vec{v})\cdot T(\vec{w}) = \vec{v}\cdot\vec{w}$
     for all $\vec{v}$, $\vec{w}$

Null vector
:    A vector $\vec{v}$ is **null** $\Leftrightarrow Q(\vec{v}) = 0$ (only
     $\vec{0}$ for Euclidean dot product, many more for others)

Geometry in $\mathbb{V}^n$
===========================

Transformations
---------------
Projection
:   The projection $P_{\vec{v}}(\vec{w})$ of a vector $\vec{w}$ onto a vector $\vec{v}$
    is the vector $\vec{u}$ which is in the direction of $\vec{v}$ and satisfies
    $(\vec{w}-\vec{u})\perp\vec{v}$:

    \begin{equation*}
    P_{\vec{v}}(\vec{w}) = \frac{\vec{v}\cdot\vec{w}}{\vec{v}\cdot\vec{v}}\vec{v}
                         \quad = \frac{\vec{v}\:\vec{v}^T}{\vec{v}^T\vec{v}}\:\vec{w}
    \end{equation*}

    Properties: $P_{\lambda\vec{v}}(\vec{w}) = P_{\vec{v}}(\vec{w})$ \qquad
                $P_{\vec{v}}(\lambda\vec{w}) = \lambda P_{\vec{v}}(\vec{w})$ \qquad
                $P_{\vec{v}}(\vec{w_1} + \vec{w_2}) = P_{\vec{v}}(\vec{w_1}) + P_{\vec{v}}(\vec{w_2})$ \qquad


Reflection in the vector $\vec{v}$
:   \qquad $R_{\vec{v}}(\vec{w}) = 2 \frac{\vec{v}\cdot\vec{w}}{\vec{v}\cdot\vec{v}}\vec{v} - \vec{w}$
    \qquad $R_{\vec{v}}^2(\vec{w})=\vec{w}$ (involution)
    \qquad isometry

Reflection conjugation
:    $R_{\vec{v}}(\vec{w}) = \vec{u} \;\rightarrow\; R_{\vec{v}} \circ R_{\vec{w}} \circ R_{\vec{v}} = R_{\vec{u}}$

Rotation around $\vec{0}$
:    Definition should be independent of any prior Euclidean/physical
     intuition. $\rightarrow$ A rotation is a composition of two reflections.
     $R_{\vec{v_1},\vec{v_2}} := R_{\vec{v_2}} \circ R_{\vec{v_1}}$

Theorems
--------

Pythagoras
:    $\vec{v_1} \perp \vec{v_2} \quad\Leftrightarrow\quad Q(\vec{v_1}) + Q(\vec{v_2}) = Q(\vec{v_1}\pm\vec{v_2})$


\pagebreak

Geometry in $\mathbb{V}^2$ (planar)
===================================

Lines
-----
Lines can be represented in three forms:

 - Cartesian: $ax+by=c$

 - point-normal form: through point $A$ ($\vec{a}$) with normal
   $\vec{n}=\scriptsize\left(\begin{array}{c}a\\b\end{array}\right)$:
   $\vec{n}\cdot(\vec{x}-\vec{a})=0$
   $\rightarrow$ $\vec{n}\cdot\vec{a}=c$

 - parameterized: through point $A$ ($\vec{a}$) with direction
   $\vec{v}=\scriptsize\left(\begin{array}{c}-b\\a\end{array}\right)$:
   $\vec{x}=\vec{a} + \lambda\vec{v}$

Quadrance from point $A$ to line $l:\vec{n}\cdot(\vec{x}-\vec{a})=0$:
:   $Q(\vec{a}, l) = \frac{1}{\vec{n}\cdot\vec{n}}[\vec{n}\cdot(\vec{a}-\vec{v})]^2$

Circles
-------
 - A circle (centered at $\vec{0}$) is a symmetric bilinear equation
   $C: \vec{v_1}\cdot\vec{v_2} = x_1x_2 + y_1y_2 = k$

 - A pair of vectors $\vec{v_1}$, $\vec{v_2}$ are **conjugate**/**dual** wrt. $C$
   $\Leftrightarrow\; \vec{v_1}\perp{}_{\!C}\:\vec{v_2} \;\Leftrightarrow\; \vec{v_1}\cdot\vec{v_2}=k$

 - A vector $\vec{v}$ lies on $C \;\Leftrightarrow\; \vec{v}\perp{}_{\!C}\:\vec{v}$
   $\Leftrightarrow\; x^2+y^2=k$ (to retrieve the familiar quadratic form)

 - For a fixed vector $\vec{v}=\scriptsize\left(\begin{array}{c}x_0\\y_0\end{array}\right)$,
   $C$ defines a line which is **dual** to $\vec{v}$: $\vec{v}^{\perp_C}: x_0 x+ y_0 y = k$

    This is the **polarity** of Appolonius.

 - For the null circle $\vec{v_1}\cdot\vec{v_2} = 0$ the duals are
   the vectors/lines which are perpendicular to the fixed vector.

 - Circles and duality work for negative $k$ as well.

 - A line $l$ is **tangent** to a circle $C$ $\Leftrightarrow$ $l$ meets $C$ in
   exactly one vector.

Theorems:

 - If $\vec{v}$ lies on $C$, then $\vec{v}^{\perp_C}$ is the **tangent line** to $C$
   at $\vec{v}$.

 - If $\vec{v_1}$, $\vec{v_2}$ lie on $C$ and the tangents
   $\vec{v_1}^{\perp_C}$, $\vec{v_2}^{\perp_C}$ meet at $\vec{u}$, then
   $\vec{u}^{\perp_C}$ passes through $\vec{v_1}$ and $\vec{v_2}$. (Graphical
   construction of dual line for a point outside of $C$)

 - If $\vec{v_1}$, $\vec{v_2}$, $\vec{v_3}$ lie on $C$ and $\vec{u_1}$,
   $\vec{u_2}$, $\vec{u_3}$ are corresponding meets of tangents, then
   the triangles $\Delta\vec{v_1}\vec{v_2}\vec{v_3}$ and
   $\Delta\vec{u_1}\vec{u_2}\vec{u_3}$ are perspective, i. e. the lines
   through $\vec{v_1}\vec{u_1}$, $\vec{v_2}\vec{u_2}$, $\vec{v_3}\vec{u_3}$
   meet in a point.

 - Appolonius: If $\vec{v_1}$, $\vec{v_2}$, $\vec{v_3}$, $\vec{v_4}$ lie on $C$, and
   $\vec{r}$, $\vec{s}$, $\vec{t}$ are the three meets of the six diagonals of
   those four points, then $\vec{r}\perp{}_{\!C}\:\vec{s}$,
   $\vec{s}\perp{}_{\!C}\:\vec{t}$, $\vec{t}\perp{}_{\!C}\:\vec{r}$. I. e. the
   lines through two of these three points are the dual line to the third
   point.


Transformations
---------------
Reflection in the line $\vec{v}\cdot\vec{x}$
:    \qquad $T_{\vec{v}}(\vec{w}) = - R_{\vec{v}}(\vec{w})$
     \qquad involution, isometry

\pagebreak

Geometry in $\mathbb{V}^3$
==========================
Planes/Spheres in 3D mostly behave like lines/circles in 2D.

Planes
------
Planes can be represented in three forms:

 - Cartesian: $ax+by+cz=d$

 - point-normal form: through point $A$ ($\vec{a}$) with normal
   $\vec{n}=\scriptsize\left(\begin{array}{c}a\\b\\c\end{array}\right)$:
   $\vec{n}\cdot(\vec{x}-\vec{a})=0$
   $\rightarrow$ $\vec{n}\cdot\vec{a}=d$

 - parameterized: through point $A$ ($\vec{a}$) with directions
   $\vec{v}$ and $\vec{w}$:
   $\vec{x}=\vec{a} + \lambda\vec{v} + \mu\vec{w}$

Spheres
-------
 - A sphere (centered at $\vec{0}$) is a symmetric bilinear equation
   $S: \vec{v_1}\cdot\vec{v_2} = x_1x_2 + y_1y_2 + z_1z_2 = k$

 - A vector $\vec{v}$ lies on $S \;\Leftrightarrow\; \vec{v}\perp{}_{\!C}\:\vec{v}$
   $\Leftrightarrow\; x^2+y^2+z^2=k$ (to retrieve the familiar quadratic form)

 - Duality between vectors and planes, tangent planes like in the 2D case.


<!--- vim: ft=markdown
-->
