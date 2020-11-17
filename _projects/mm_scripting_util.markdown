---
layout: page
title: MadMiner Scripting Utility
description: Research project with CERN Research Scientest Tancredi Carli, in the CERN ATLAS group
img: /assets/img/mmsc/mmsc_description.png
importance: 3
---

* [**Overview**](#overview)
* [**Personal Contributions**](#personal-contributions)

## Overview

In this project I worked with a recently developed likelihood-free inference framework, [**MadMiner**](https://iris-hep.org/projects/madminer.html).

This method works by training deep neural networks to approximate the likelihood function, using the joint likelihood ratio and joint score.

I worked on this project full time for about 4 months, while I was living in Geneva.

## Personal Contributions

My goal was to apply the joint-likelihood ratio estimation procedure provided by MadMiner to a number of new physics signals, all at the *parton-level*. Since parton level simulations are much easier and less time consuming to generate than detector level simulations, they provide an excellent opportunity  a probe them for feasibility.

This is illustrated below by both a successful and failed scenario. For the case of a $$ttH$$ decay, shown at right below, we determined that the strict bounds of the parameter (and localization of test cases at either extreme) was the cause of this. This indicates a possible point of weakness for the algorithm that could be addressed in the future.

<div class="row">
    <div class="col-sm mt-4 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/mmsc/ideal.png' | relative_url }}" alt="" title="ideal case"/>
    </div>
    <div class="col-sm mt-5 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/mmsc/tth_res.png' | relative_url }}" alt="" title="ttH case"/>
    </div>
</div>
<div class="caption">
    Ideal likelihood learning scenario (left) and results from the failed trial (right)
</div>

To facilitate quick testing of new signal models, I developed a command line program and python module, located [**here on github**](https://github.com/luclepot/mm_scripting_util). A screenshot of the program in action is shown below; it facilitats training, evaluation, and data/results visualization.

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-75" src="{{ '/assets/img/mmsc/mmsc_description.png' | relative_url }}" alt="" title="cli"/>
    <div class="caption">
        command line interface
    </div>
</div>

In general, this project gave me a good introduction to machine learning with PyTorch and physics simulations in Pythia/Madgraph. It also gave me a chance to greatly develop and refine my software development skills, especially using remote environments like the CERN computing grid. By the end of the project, I had committed over 50k lines of code to 3 shared repositories.

I was also very impacted by the research environment at CERN. I spent a lot of my time there meeting and talking with other researchers, and it was a fantastic introduction to the necessarily collaborative basis of particle physics research.

<!-- 
Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
``` -->
