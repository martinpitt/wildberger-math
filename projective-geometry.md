---
documentclass: scrartcl
classoption: DIV=15
title: Projective Geometry
subtitle: After [N. J. Wildberger's YouTube lecture series
 <http://www.youtube.com/watch?v=NYK0GBQVngs> et al
author: Martin Pitt (<martin@piware.de>)
header-includes: \usepackage[all]{xy}
...

Projective geometry is the geometry involving only a straightedge. It is
the fundament for affine, Euclidean, spherical, hyperbolic, and other
geometries.

Classification of geometries
============================

\xymatrix{
& & & *+[F]\txt{\textbf{Euclidean}}\\
*+[F]\txt{\textbf{Projective}\\
           only tool: straightedge\\
	   objects: points, lines\\
	   ops: join of points,\\
	   meet of lines}
\ar[r]
& *+[F]\txt{\textbf{Affine}\\
            introduce parallel lines\\
	    translation\\
	    scaling along a line\\
	    relative area\\
	    vectors\\
	    linear transformations}
\ar[r]
& *+[F]\txt{\textbf{Metrical structure}\\
            introduce null conic\\
	    defines a dot product\\
	    quadrance (distance)\\
	    spread (angle)\\
	    perpendicularity\\
	    circles}
\ar[ur]
\ar[r]
\ar[dr]
& *+[F]\txt{\textbf{Hyperbolic}}\\
& & & *+[F]\txt{\textbf{Spherical}/\\
                \textbf{Elliptical}}\\
}


Notation
========

Points:
:   projective points have lower-case variables ($a$, $p$); affine
    (Euclidean) points have upper-case variables ($A$, $P$); the product
    of two points $ab$ is the line that goes through $a$ and $b$

Lines:
:   projective lines have upper-case variables ($L$, $M$); affine lines
    have lower-case variables ($l$, $m$); the product of two lines $AB$
    is their intersection, i. e. a point

\pagebreak

Important Theorems
==================

Pappus’ Theorem:
:   If $a_1, a_2, a_3$ are collinear and $b_1, b_2, b_3$ are collinear:\
    $c_1 := (a_2b_3)(a_3b_2)$, $c_2:=(a_1b_3)(a_3b_1)$,
    $c_3 := (a_2b_3)(a_3b_2)$ are collinear.

Pascal’s Theorem:
:   If $a_1, a_2, a_3, b_1, b_2,b_3$ are points on a conic:\
    $c_1 := (a_2b_3)(a_3b_2)$, $c_2:=(a_1b_3)(a_3b_1)$,
    $c_3 := (a_2b_3)(a_3b_2)$ are collinear.

Desargues Theorem:
:   If two triangles $\overline{a_1a_2a_3}$ and $\overline{b_1b_2b_3}$
    are perspective from a point $p$, i. e. $a_1b_1$, $a_2b_2$, $a_3b_3$
    are concurrent; then they are perspective from a line $L$, where
    $(a_1a_2)(b_1b_2)$, $(a_2a_3)(b_2b_3)$, $(a_3a_1)(b_3b_1)$ are
    collinear).

Perspectivity
=============
In arts, photography, etc., one often has a horizon and perspective. In
these projections, these rules hold:

 - Lines are projected to lines.

 - All parallel lines meet at a point on the horizon (“point at infinity”).
   There is one point on the horizon for each family of parallel lines.

- Conics are projected to conics. E. g. a parabola or a hyperbola will look
  like an ellipse. All conics will look elliptic as they originate from slicing
  a cone.

Projective homogeneous coordinates
==================================

In affine geometry, lines from a 3D object through the projective plane
are parallel, and projections maintain linear spacing. In projective
geometry, they meet in two points (“observer” or ”horizon”), and
projections distort linear spacing.

In **one-dimensional geometry**, the projective line $\mathbb{P}^1$ is
the space of one-dimensional subspaces of the two-dimensional
$\mathbb{V}^2$, i. e. a line through $[0,0]$. This is specified by a
proportion $[x:y]$ (**projective point**); canonically, either $[x:1]$,
or $[x:0]$ for the special case of the subspace being the x axis
(representing “point at $\infty$”)

In **two-dimensional geometry**, the projective plane $\mathbb{P}^2$ is
described with a three-dimensional vector space $\mathbb{V}^3$,
**projective points** $a=[x:y:z]$ (lines through the origin) and
**projective lines** $A=(l:m:n) \Leftrightarrow lx+my+nz = 0$ (planes
through the origin).

In particular, we introduce a **viewing plane** $y$~z=1~. Then any
projective point $[x:y:z], z\neq 0$ meets the viewing plane at
$[\frac{x}{z}:\frac{y}{z}:1]$. Any projective point $[x:y:0]$
corresponds to the two-dimensional equivalent $[x:y]$, representing the
“point at $\infty$ in the direction $[x:y]$”. So the projective plane
$\mathbb{P}^2$ corresponds to the affine plane $\mathbb{A}^2$ plus the
projective line $\mathbb{P}^1$ for the points at infinity.

Any projective line $(l:m:n), l,m \neq 0$ meets the viewing plane at the
line $lx+my=n$.

Coordinates in the viewing plane are called $X:=\frac{x}{z}$ and
$Y:=\frac{y}{z}$.

This introduces a duality between lines and points: Any theorem has a
dual counterpart where lines and points, meets and joins etc. are
interchanged.

Calculations with homogenous coordinates
========================================

Join of points:
:   If $a = [x_1:y_1:z_1]$ and $b = [x_2:y_2:z_2]$, then

    $ab = (y_1z_2 - y_2z_1 : z_1x_2 - z_2x_1 : x_1y_2 - x_2y_1)$

Meet of lines:
:   If $L = (l_1:m_1:n_1)$ and $M = (l_2:m_2:n_2)$, then

    $ab = [m_1n_2 - m_2n_1 : n_1l_2 - n_2l_1 : l_1m_2 - l_2m_1]$

Incidence:
:   The point $[x:y:z]$ and the line $(l:m:n)$ are incident
    $\Leftrightarrow lx + my + nz = 0$

Linear transformation:
:   A linear transformation
    $(x, y) \to (x', y') = (x\: y)\left(\begin{array}{cc}a & b\\c & d\end{array}\right)$
    is represented homogeneously with
    $[x:y:z] \to [x':y':z'] = [x\: y\: z]\left[\begin{array}{ccc}a & b & 0 \\c & d & 0\\ 0 & 0 & 1\end{array}\right]$

Affine transformation:
:   A translation (non-linear) $(x, y) \to (x + a, y + b)$ is
    represented homogeneously with
    $[x:y:z] \to [x':y':z'] = [x \: y \: z]\left[\begin{array}{ccc}1 & 0 & 0 \\0 & 1 & 0\\ a & b & 1\end{array}\right]$
    $= [x + az: y + bz : z]$

Metrical structure
==================

Add a “null conic” ${\mathcal C}$ to the geometry by
defining a (homogeneous) symmetric matrix
$A=\left[\begin{array}{ccc}a & d & f\\ d & b & g\\ f & g & c\end{array}\right]$

For any point $p = [x:y:z]$, setting $p A p^T = 0$ expands to the
general equation of a homogeneous conic:
$ax^2 + by^2 + cz^2 + 2dxy + 2fxz + 2gyz = 0$

When dividing by $z^2$ we get the affine coordinates:
$aX^2+bY^2+ 2dXY + 2fX + 2gY + c = 0$

This matrix $A$ defines a symmetric bilinear form (**dot/inner product**)
on $\mathbb{V}^3$: $v\cdot w := vAw^T$

The usual **Euclidean** one is
$A_E=\tiny\left[\begin{array}{ccc}1 & 0 & 0\\ 0 & 1 & 0\\ 0 & 0 & 1\end{array}\right]$
but there are other interesting ones too, like the **relativistic**
(Lorentz, Minkowski, Einstein) structure
$A_R=\tiny\left[\begin{array}{ccc}1 & 0 & 0\\ 0 & 1 & 0\\ 0 & 0 & -1\end{array}\right]$.

This defines the notion of **perpendicularity**:
$p \perp q \Leftrightarrow p\cdot q = pAq^T = 0$. This is well-defined
projectively and in $\mathbb{P}^2$.

Polarity
========

$aAb^T = 0$ can be interpreted as $a(Ab^T) = 0$ and since $L := Ab^T$
defines a line, as $aL = 0$. I. e. the dot product defines a duality
between points and lines, called **polarity**.

Pole:
:   The pole $a$ of a line $L$ is the inversion point of $L$’s closest
    point to ${\mathcal C}$. $\mathbf a = L^\perp$

Polar:
:   The line $L$ is the polar of the pole point $a$. $\mathbf L = a^\perp$

\pagebreak

**Construction of polar of $a$:**

 - Find “null points” $\alpha, \beta, \gamma, \delta$ on
   ${\mathcal C}$ so that
   $(\alpha\beta)(\gamma\delta) = a$ (i. e. select two secants of
   ${\mathcal C}$ which pass through $a$)

 - Define $b := (\alpha\delta)(\beta\gamma)$ and $c :=
   (\alpha\gamma)(\beta\delta)$, i. e. the two intersections of
   the other diagonals of the quadrangle $\alpha\beta\gamma\delta$

 - Then $A = a^\perp = bc$. Also, $b^\perp = ac$ and $c^\perp = ab$
   (three-fold symmetry of polars and poles produced by the three
   intersections of diagonals)

 - **Polar Independence Theorem:** The polar $A = a^\perp$ does not
   depend on the choice of lines through $a$, i. e. the choice of
   $\alpha, \beta, \gamma, \delta$.

**Construction of pole of $A$:** Choose any two points $b, c\in A$. Then
$a = (b^\perp c^\perp)$.

**Construction of polar of null point $\gamma$:**

 - Chose any two secants $A$, $B$ that pass through $\gamma$

 - Construct their poles $A^\perp$, $B^\perp$

 - Polar $\Gamma = \gamma^\perp$ is the tangent $(A^\perp B^\perp)$

**Polar Duality Theorem:** For any two points $a$ and $b$:
$a\in b^\perp \Leftrightarrow b\in a^\perp$ (as $A$ is symmetric)

<!--- vim: ft=markdown
-->
