---
layout: post
title:  "A bunch of methods for solving ordinary differential equations"
date:   2018-2-20 07:51:12 +0800
categories: jekyll update
---


<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


<b> Forced heat and forced wave (homogenous boundary conditions)</b>

<i>Forced Heat</i>

$$ \theta_{t} - D\theta_{xx} = f(x,t), \text{ } \theta(x, 0) = 0$$. 

<ul>
<li> Assume fourier transform exists for f(x, t). </li>
<li> Solve for Green's function then apply it. </li>
</ul>

Stage 1: 

The required Green's function: '

$$ \frac{\partial G(x, t; \xi, \tau)}{\partial t} - D \frac{\partial ^{2}G(x, t; \xi, \tau)}{\partial x^{2}} = \delta(x - \xi)\delta(t - \tau), G(x, 0; \xi, \tau) = 0.$$

Fourier tranforming in $$ x $$

\begin{align}
\frac{\partial}{\partial t}(e^{Dk^{2}t}\hat{G}(k, t; \xi, \tau)) &= e^{-ik^{2}+Dk^{2}}\delta(t - \tau)
\end{align}


<b> Forced Laplace's equation on a domain $$ D $$ with boundary conditions </b>

The equation to solve: 

<center>
$$ \nabla^{2} u = -f(\mathbf{x}), \text{ }u = 0 \text{ on } \delta D$$
</center>

Step 1: Remind youself of the multidimensional Green's function (either in 2D or 3D). 

<center>
$$\delta(\mathbf{r}-\mathbf{r_{0}}) = 0, \text{ } \forall \mathbf{r} \neq \mathbf{r_{0}}, \text{ } \int_{D}\delta({\mathbf{r} - \mathbf{r_{0}}}) = 1 \text{ when } \mathbf{r_{0}} \in D, \text{} 0 \text { otherwise.}
$$
</center>


Step 2: Define the "free space" Green's functions in 2D and 3D.  

<center>
$$ \nabla^{2}G_{f}(\mathbf{r}; \mathbf{r_{0}}) = \delta(\mathbf{r}-\mathbf{r_{0}}) $$
</center>

and assuming spherical symmetry and replacing $$ \mathbf{r_{0}}$$ at the origin, $$ G(\mathbf{r}; \mathbf{r_{0}}) = G(r)$$. 

Now we can use a limiting case; cut out a little ball at $$ \mathbf{r_{0}}$$ so that the function is defined there, and we get that 

<center>
$$ \int_{V_{\epsilon}} \nabla^{2} G(\mathbf{r}; \mathbf{r_{0}}) = 0 = \int_{S_{R}} \nabla G_{f}(r).\hat{\mathbf{n}} dS  - \int_{S_{\epsilon}} \nabla G_{f}(r).\hat{\mathbf{n}} dS$$
</center>


But we know the limiting case as $$ \epsilon \rightarrow 0 $$. So taking the needed surface integral we get: 

<ul>
<li> In 3D: $$ 4 \pi r^{2} \frac{dG}{dr} = 1 \implies G = \frac{-1}{4\pi r} = \frac{-1}{4 \pi |\mathbf{r} - \mathbf{r_{0}}|}$$ </li>
    
<li> In 2D, similarly we have $$G(r) = \frac{log |\mathbf{r} - \mathbf{r_{0}}|}{4 \pi} $$</li>
</ul>

Step 3: Use Green's Identities to our advantage

Use Green's second identity, take the standard "limiting case", then plug in our free space Green's functions.
<center>

\begin{align}
\int_{V_{\epsilon}} (u \nabla^{2}G_{f_{3}} - G_{f_{3}} \nabla^{2}u)dV &= \int_{V_{\epsilon}}G_{f_{3}}f(\mathbf{r}) dV \\
& = \int_{S} u \frac{\partial G_{f_{3}}}{\partial n} - G_{f_{3}}\frac{\partial u}{\partial n} \\
& + \int_{S_{\epsilon}} u \frac{\partial G_{f_{3}}}{\partial n} - G_{f_{3}} \frac{\partial u}{\partial n} dS. 
\end{align}

</center>

This is well behaved. We can show, by subsituting in the Green's functions that the 3rd term actually tends to $$ -u(\mathbf{0})$$, and that the 3rd term vanishes. So we finally get

<center>
\begin{align}
u(\mathbf{r_{0}}) &= \int_{V}G_{f_{3}}(\mathbf{r}; \mathbf{r_{0}}) dV  \\
& + \int_{S} (u\frac{\partial G(\mathbf{r}; \mathbf{r_{0}})}{\partial n}) - G(\mathbf{r}; \mathbf{r}) \frac{\partial U}{\partial n} dS
\end{align}
</center>

Step 4: Applying dirichlet conditions

Just in the dirichlet case, if: 

$$ \nabla^{2} u = -f $$ in $$ D$$, and $$ u = h(\mathbf{r})$$ on $$ \delta D$$: 

$$ G(\mathbf{r}, \mathbf{r_{0}}) $$ has continuous second derivatives, and satistfies Lapace's equation everywhere in $$ D $$ except in $$ \mathbf{r_{0}}$$, $$ G(\mathbf{r}; \mathbf{r_{0}}) = 0 $$ on the boundary
 $$ H = G - G_{f_{3}} $$ is finite at $$ \mathbf{r_{0}}$$, has continuous second derivatives and obeys Laplaces equation at $$ \mathbf{r_{0}}$$. 

Use Green's third and second identities with H and G, with the boundary conditions to get,

<center>

$$ u (\mathbf{r_{0}}) = \int_{\delta D} h(r)\frac{\partial G(\mathbf{r};\mathbf{r_{0})}{\partial n}$$
$$ + \int_{D} -f(\mathbf{u}) G(\mathbf{r}; \mathbf{r_{0}}) dV $$

</center>

