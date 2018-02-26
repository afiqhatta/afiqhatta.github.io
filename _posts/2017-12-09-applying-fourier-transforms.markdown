---
layout: post
title:  "Linking Fourier Transforms and Green's functions, the Philosphy of Causality"
date:   2017-12-09 07:51:12 +0800
categories: jekyll update
---


<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


<b>
Heat
</b>

Given that I can figure out the inverse fourier transforms to some standard functions, this proves a really effective technique for working through partial differential equations. What is essentially going on? Well, we're taking a difficult equation, transforming it to make it a little simpler to deal with (which in this case we call the spectral space). But the cool part is that now we are in the realm of "easier results". Now that we've done this, we flip everything back. 

The hard part is just trying to flesh the standard results out in this new space, we gotta use some tricks. Let's consider a example of heat dispersing on a bar which is infinite. In the topic I wrote about well posed problems, I looked at what type of conditions we need for the problem to make sense. Turns out an "initial" distribution is enough for us to have a "well posed" problem". 

We know the model has to obey
<center>
$$ \frac{\partial \theta}{\partial t} = D \frac{\partial^{2}\theta}{\partial x^{2}},$$
</center>

where  $$ D $$ is a constant (which we call the thermal diffusivity sometimes). 

Suppose the model has some intial distribution of heat (could be a normal distribution, pulse or whatever one pleases) which is 

<center>
$$ \theta(x, 0) = \Theta (x). $$  
</center>

How do we get started? Well, to break down the problem we can use the following steps I like to do; 

<ul>
    <li> Select just the \( x \)  variable and transform the equation. Remeber that partial differentiation now becomes multiplication! We switch out the \( x \) variable with another variable say \( k \). </li>
    <li> Solve this simpler problem using standard technqiues, remember to transform the boundary conditions too to find the mutlplicative constant. </li>
    <li> We're all set to apply our convolution formula. All we have to do now is find the pesky function which gives us the Gaussian term in the product! </li>
</ul>

Try work out the algebra yourself!

Trying this method out on the wave equation gives

Now, we can construct a nice link with what we know about Green's functions too! Let's try attack the problem with what we know about Green's functions. Let's list out some good-to-know properties: 

<ul>
    <li> Green's functions are best applied in situations with forcing because by construction they satisfy the equation but the forcing are dirac delta functions this time! </li>
    <li> They still play nice with the boundary conditions. </li>
    <li> We can still use the in fourier transforms to try break into the spectral space. </li>
</ul>

So as before, suppose we had another heat equation problem that we wanted to tackle. Try turning into a Green's function problem, and then use a Fourier transform on the Dirac delta function to get what you want. But then finally be careful with your bounds of integration to get the required result. 


<b>
Waves
</b>

We can have a shot applying some of these ideas for waves as well. Although in this case, we need to be careful as it would be much easier to recall some previous results from Dirichlet's discontinuous formula. '

<b>
Causality and philosophy
</b>

You may have noticed the dependence of the solution at a given time as the integral of some function in the bounds between zero and the current time. This is proof of causaility in events that occur. 
