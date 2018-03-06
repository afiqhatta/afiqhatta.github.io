---
layout: post
title:  "Fluids"
date:   2018-3-1 07:51:12 +0800
categories: jekyll update
---


<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

<h2>Viscous flow types</h2>

Vicous flow is characterised by a thin boundary layer of fluid between the fluid and its boundary. This enables the <b>no slip condition</b>, where $$ \mathbf{u} = 0 $$ on the boundary, where $$ \mathbf{u}$$ is the velocity field of the fluid. 

The tangential shear stress exerted by a fluid on a surface is given by 
<center>
$$ \tau = \mu \mathbf{n} \cdot \nabla \mathbf{u}.$$
</center>

The normal is pointing from the surface into the fluid. The shear stress is in the direction of the fluid. 

<h1>Navier stokes equations for an incompressible fluid</h1>

We're familiar with the regular Euler equation, but we can add the viscous term as follows: 

<center>
$$ \frac{\partial \mathbf{u}}{\partial t} + \mathbf{u} \cdot \nabla \mathbf{u} = -\frac{\nabla p}{\rho} + \nu \nabla^{2}\mathbf{u} + \mathbf{F}$$ 
</center>

which is also paired with the continuity equation

<center>
$$ \nabla \cdot \mathbf{u} = 0 $$. 
</center>

This is solved with the no-slip boundary condtion. 

<h1>The Reynolds Number (Re)</h1>

We can characterise the turbulence level of a flow by deriving the Reynolds number from the characteristic length $$ L $$, speed $$ U $$, and the viscocity $$ \nu $$. 

<center>
$$  Re = \frac{UL}{\nu}$$
</center>

We can compare the magintude of the inertia and the viscous terms. 

<ul>
<li>The inertia term \( |(\mathbf{u} \cdot \nabla) \mathbf{u}| = O(U^{2}/L)  \)</li>
<li>The viscous term \(|\nu \nabla^{2} \mathbf{u}| = O(U/ \nu L^{2}) \) </li>
</ul>

So the inertia term over the viscuous term gives a term of $$ O(Re) $$. 

<b>High Reynolds number: </b>fluid motion with small viscocity. There's a characteristic boundary layer thickness. The larger the Reynolds number, the smaller the thickness. 

<b>Low Reynolds number flow: </b>

Time and inertial terms become insignificant. So we have $$ \nabla \cdot \mathbf{u} = 0 $$

<center>
0 = - \nabla p + \mu \nabla^{2} \mathbf{u}. 
</center>

<h1>Simple viscous flows</h1>

<b>Plane parallel shear flow</b> is of the form: 

Apply NS with boundary conditions to get 
<ul>
    <li>Couette flow</li>
    <li>Poissielle flow</li>
</ul>



