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

What's maybe more interesting is that we even an initial distribution may not be enough to specify what's going on fully. We may need to take into account boundary temperatures too. '





Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
