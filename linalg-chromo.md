---
documentclass: scrartcl
classoption: DIV=15
title: Chromatic Linear Algebra and Complex Numbers
subtitle: After [N. J. Wildberger's YouTube lecture series](<https://www.youtube.com/watch?v=nJdWFoliRnc&list=PL01A21B9E302D50C1&index=40>)
author: Martin Pitt (<martin@piware.de>)
header-includes: \setcounter{secnumdepth}{2}
...

\newcommand{\mtwo}[1]{\scriptsize\left(\begin {array}{cc} #1 \end {array}\right)}

Triality of planar geometry
===========================

Introduction of three different dot products:

                                   Blue (Cartesian)          Red (relativistic)          Green (relativistic)
----------                         ----------------          ------------------          --------------------
$(x_1,y_1)\cdot(x_2,y_2)$          $x_1x_2+y_1y_2$           $x_1x_2-y_1y_2$             $x_1y_2+x_2y_1$
Dot product matrix                 $\mtwo{1&0\\0&1}$         $\mtwo{1&0\\0&-1}$          $\mtwo{0&1\\1&0}$
$Q((x,y))$                         $x^2+y^2$                 $x^2-y^2$                   $2xy$
Perpendicular of $\vec{v}=(x,y)$   $\vec{v}_\perp^b=(-y, x)$ $\vec{v}_\perp^r=(y, x)$    $\vec{v}_\perp^g=(x, -y)$

$Q_b^2 = Q_r^2 + Q_g^2$

A fourth (non-symmetric) matrix
$A_p:=\scriptsize\left(\begin{array}{cc}0&1\\-1&0\end{array}\right)$ encodes
parallelism:

$(x_1,y_1) || (x_2,y_2) \;\Leftrightarrow\; (x_1,y_1)A_p(x_2,y_2)=0$.
Together with the three dot product matrices these are a basis of the space of
2x2 matrices.

Isometries
==========
We look for matrices $A$ satisfying $\vec{v}\cdot\vec{w}=(\vec{v}A)\cdot(\vec{w}A)$
for all $\vec{v}$, $\vec{w}$. If $\vec{v}\cdot\vec{w}=\vec{v}M\vec{w}^T \; \Rightarrow \; M=AMA^T$.

These matrices satisfy this requirement ("rotations"):

Blue                               Red                               Green
----------------                   ------------------                --------------------
$\mtwo{s&r\\-r&s}$ if $s^2+r^2=1$  $\mtwo{s&r\\r&s}$ if $s^2-r^2=1$  $\mtwo{s&0\\0&r}$ if $sr=1$

Complex numbers
===============

We define complex numbers as subspaces of 2x2 matrices.
Each is closed under addition, scalar multiplication, and matrix multiplication.
We define unit constants to write those in simpler form:

                        Blue                             Red                              Green
----------              ----------------                 ------------------               --------------------
matrix form             $\mathbb{C}_b: \mtwo{a&b\\-b&a}$ $\mathbb{C}_r: \mtwo{a&b\\b&a}$  $\mathbb{C}_g: \mtwo{a&0\\0&b}$
"imaginary" constant    $i:=\mtwo{0&1\\-1&0}$            $j:=\mtwo{0&1\\1&0}$             $k:=\mtwo{1&0\\0&-1}$
                        $i^2=-1$                         $j^2=1$                          $k^2=1$
Simple form             $aI + bi$                        $aI + bj$                        $\frac{a+b}{2}I + \frac{a-b}{2}k$

With these constants, the following hold:
$ij=k$, $kj=i$, $ki=j$, $ji=-k$, $jk=-i$, $ik=-j$ ("dihedrons"; *different* from quaternions!)


<!--- vim: ft=markdown
-->
