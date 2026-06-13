---
layout: post
title:  "Moving Subspaces"
date:   2026-06-12 07:00:00 +0100
categories: "movingframes"
---

<p align="center">
  <img src="/Pictures/TileMesh2_800w.jpg" alt="Square Triangle Tiling"/>
</p>

<ul>
<li>Back to the <a href="/topics/movingframes">Moving Frames</a> category index.</li>
</ul>

Let $M=\mathbb{S}^{n-1} \times \mathbb{R}^{m}$ with $n > 1, m > 0$. 
Let $\pi, \iota$ be the usual projection and inclusion maps:
$$
\begin{array}{l}
\pi \colon \mathbb{S}^{n-1} \times \mathbb{R}^{m} \twoheadrightarrow \mathbb{S}^{n-1} \\
\iota \colon \mathbb{S}^{n-1} \times \mathbb{R}^{m} \hookrightarrow \mathbb{R}^{n+m}
\end{array}
$$

<h2>1. Exponential Map</h2>

Let $x \in M, v \in T_{x}M$. Define the exponential map in $x$, $\exp_x \colon T_{x}M \rightarrow \mathbb{R}^{n+m}$ (we will later show that indeed $\Im(\exp_x) \sube M$) as

$$
\begin{align}
\exp_x(v)=\cos(\lVert\pi(v)\rVert)x + \sin(\lVert\pi(v)\rVert) \frac{v}{\lVert\pi(v)\rVert}
\end{align}
$$

For $t \in \mathbb{R}$ we have

$$
\begin{align}
\exp_x(tv)=\cos(t\lVert\pi(v)\rVert)x + \sin(t\lVert\pi(v)\rVert) \frac{v}{\lVert\pi(v)\rVert}
\end{align}
$$

which can easily be checked by substituting $tv$ to $v$ in  the previous expression and performing some simple calculations, relying on the fact that $\pi$ is linear and that the norm is (positive) multiplicative. The last step involves taking $\text{sgn}(t)$ inside $\sin$ using the oddness of the sine function.

<h3>Property 1</h3>

The image of the exponential curve is contained in the 2-dimensional vector subspace of $\mathbb{R}^{n+m}$ spanned by $x$ and $v$:

$$
\begin{align}
\forall t \in \mathbb{R}, \exp_x(tv) \in \braket{x,v} \le \mathbb{R}^{n+m}
\end{align}
$$

<h4>proof</h4>

$$
\exp_x(tv) = \alpha x + \beta v
$$

with

$$
\begin{array}{l}
\alpha = \cos(t\lVert\pi(v)\rVert) \\
\beta = \frac{\sin(t\lVert\pi(v)\rVert)}{\lVert\pi(v)\rVert}
\end{array}
$$

<h3>Property 2</h3>

The image of the exponential curve is in $M$, i.e. the norm of its projection is $1$:

$$
\begin{align}
\forall t \in \mathbb{R}, \lVert\pi(\exp_x(tv))\rVert = 1
\end{align}
$$

<h4>proof</h4>

$$
\pi(\exp_x(tv)) = \cos(t\lVert\pi(v)\rVert)\pi(x) + \frac{\sin(t\lVert\pi(v)\rVert)}{\lVert\pi(v)\rVert} \pi(v)
$$

because $\pi$ is linear. Now, since $v \in T_{x}M$, $\pi(v) \in T_{\pi(x)}\mathbb{S}^{n-1}$ and since this is a sphere, we know that $\pi(v) \perp \pi(x)$. So, by Pythagoras

$$
\lVert\pi(\exp_x(tv))\rVert^2 = \cos^2(t\lVert\pi(v)\rVert)\cdot \lVert\pi(x)\rVert^2 + \frac{\sin^2(t\lVert\pi(v)\rVert)}{\lVert\pi(v)\rVert^2} \cdot \lVert\pi(v)\rVert^2
$$

Since $x \in M$, $\lVert\pi(x)\rVert = 1$. So

$$
\lVert\pi(\exp_x(tv))\rVert^2 = \cos^2(t\lVert\pi(v)\rVert) + \sin^2(t\lVert\pi(v)\rVert) = 1
$$

The norm is positive, so it's enough to take the square root in order to finish the proof.

___

<h3>Notes and References:</h3>
