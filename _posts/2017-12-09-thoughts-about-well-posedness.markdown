---
layout: post
title:  "Thoughts about well-posed Problems"
date:   2017-12-09 07:51:12 +0800
categories: jekyll update
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>



Let's say we want to model some real-life situation. For example, if we want to model the heat flow of some kind of system, say, we would start by attempting to solve the heat equation: 

<center>
$$ \frac{\partial \theta^{2}}{\partial t}  = \nabla^{2} \theta. $$
</center>
But now we have an issue. The equation on it's own isn't really enough to tell us what's going on. We would need to set the problem up in the right way for it to make any sense. Firstly, what's the shape of the object we are acting on with the heat? It could be; 

<ul>
    <li> A bar of length \( l \).</li>
    <li> A disk of some radius.</li>
</ul>

<body>
But even though we have the shape, we need to describe how the problem is set up. In the heat example, this may be to do with how the heat is set up and the end points, and how the heat distribution is initally! If we descibe the heat as \(\theta=\theta(x, t)\), then we may wish to specify that on a bar of length \(l\), 

</body>
<center>
$$ \theta(x, 0)  = x, \text{ } 0 \leq x \leq l $$
</center>

<body>
But the question is; what liberties can we take in terms of data to ensure that what we get out of the model makes any sense whatsoever?
</body>

In fact, we might even relate this to initialising some data in a class which describes an object, in Python we might have for example a bar represented by a list of list of temperatures. Each list represents a given time, and within each list each temperature represents a position. Maybe more on data structures we could use later. 

{% highlight python %}
class Bar: 
    def __init__(self, initial_distribution, time, length, temp): 
        self.length  = length
        self.time = time
        
        """
        Here we would need to specifiy what the
        intial heat shape at the discrete points look like. 
        """
        self.intial_distribution = initial_distribution
{% endhighlight %}

What's maybe more interesting is that even an initial distribution may not be enough to specify what's going on fully. We may need to take into account boundary temperatures too. 

Let's look at some examples of when a question is ill-posed. For example, if we're trying to back-track an equation in reverse time, like for example the reverse diffusion eqution (often part of a class of larger problems called inverse problems); 

<center>
$$ \frac{\partial^{2} \theta}{\partial x^{2}} + \frac{\partial \theta}{\partial x} = 0 $$
</center>

then solving this equation leads to a situation where the final solution is really senstive to in initial distribution. In this case, the intial distribution is like the "final heat measurement" one makes. 





The idea about method of characteristics lies in structuring a path where we can follow the boundary conditions. We try to parametrize across the boundary conditions, and then use that information to inspect some identities about the 'tangent' vector involved.

For example, suppose we had the problem

<center>
$$ 3y u_{x} + 2xu_{y} = 0 . \text{ } u = \sin(x) \text{ on } (x, 0)$$ 
</center>

This problem's quite nice because we have some slight asymmetry here in the coeffecients. Also have a look at the boundary condition, this also looks quite simple to parametrize across. 
What we have to do is nicely parametrize the characteristics; the lines where the solution is constant. 

<b>
Characteristics for hyperbolic PDEs. 
</b>

When we have an 2nd order PDE, then we need to reduce it to a nicer form called the "canonical form". This can be done by identifying the characteristics. First we factorize, then look at the 2nd order stuff to determine what's going on with them. The first order things we already know how to deal with. The we can make a change of variables. ' 

