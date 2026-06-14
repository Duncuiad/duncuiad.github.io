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

<h4><u>proof</u></h4>

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

<div style="text-align: right"> ∎ </div>

<h3>Property 2</h3>

The image of the exponential curve is in $M$, i.e. the norm of its projection is $1$:

$$
\begin{align}
\forall t \in \mathbb{R}, \lVert\pi(\exp_x(tv))\rVert = 1
\end{align}
$$

<h4><u>proof</u></h4>

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

The norm is positive, so it's enough to take the square root in order to complete the proof.

<div style="text-align: right"> ∎ </div>

<h3>Property 3</h3>

$$
\begin{align}
\frac{d}{dt} \exp_x(tv) = \cos(t\lVert\pi(v)\rVert) v - \lVert\pi(v)\rVert \sin(t\lVert\pi(v)\rVert) x
\end{align}
$$

<h4><u>proof</u></h4>

Just the ordinary derivative of property 1.

<div style="text-align: right"> ∎ </div>

In particular, we have

$$
\begin{align}
\forall t \in \mathbb{R}, \frac{d}{dt} \exp_x(tv) \in \braket{x,v} \le \mathbb{R}^{n+m}
\end{align}
$$

<h3>Property 4</h3>

The angular velocity (the velocity of the projection) of the exponential curve is constant and equal to $\pi(v)$

$$
\begin{align}
\forall t \in \mathbb{R}, \left\| \frac{d}{dt} \pi \left( \exp_x(tv) \right) \right\| = \lVert\pi(v)\rVert
\end{align}
$$

<h4><u>proof</u></h4>

$\pi$ is a linear projection, so

$$
\begin{array}{rl}
\frac{d}{dt} \pi \left( \exp_x(tv) \right) &= \pi \left( \frac{d}{dt}  \exp_x(tv) \right) \\
&= \cos(t\lVert\pi(v)\rVert) \pi(v) - \lVert\pi(v)\rVert \sin(t\lVert\pi(v)\rVert) \pi(x)
\end{array}
$$

$\pi(v) \perp \pi(x)$, thus 

$$
\begin{array}{rl}
\left\| \frac{d}{dt} \pi \left( \exp_x(tv) \right) \right\|^2 &= \cos^2(t\lVert\pi(v)\rVert) \cdot \lVert\pi(v)\rVert^2 + \lVert\pi(v)\rVert^2 \cdot \sin^2(t\lVert\pi(v)\rVert) \cdot \lVert\pi(x)\rVert^2 \\
&= \lVert\pi(v)\rVert^2 \cdot \left( \cos^2(t\lVert\pi(v)\rVert) + \sin^2(t\lVert\pi(v)\rVert) \right) \\
&= \lVert\pi(v)\rVert^2
\end{array}
$$

<div style="text-align: right"> ∎ </div>

<h3>Property 5</h3>

If $m = 0$, i.e. $M = \mathbb{S}^{n-1}$ for some $n > 1$, then this exponential map is just the usual spherical exponential. Just substitute using $\pi(v) = v$:

$$
\begin{align}
\begin{array}{rl}
\exp_x(v) = \cos(\lVert v \rVert) x + \sin(\lVert v \rVert) \frac{v}{\lVert v \rVert} & \text{if $m = 0$}
\end{array}
\end{align}
$$

___

<h3>Notes and References:</h3>
