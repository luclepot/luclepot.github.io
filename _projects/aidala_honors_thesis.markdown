---
layout: page
title: hardware testing & honors thesis
description: Research project / honors thesis work with University of Michigan professor Christine Aidala
img: /assets/img/aidala/aidala_sipms.PNG
importance: 2
---

## overview

One of the requirements for honors physics students at UofM is to complete a senior [honors thesis](https://lsa.umich.edu/physics/undergraduate-students/major---minor-programs/honors-physics.html#:~:text=Honors%20Concentration%20in%20Physics,-Regular%20departmental%20requirements&text=Must%20elect%20six%20credits%20of,supervision%20of%20a%20faculty%20member.). When I returned to Michigan after my research projects [at CERN](/projects/mm_scripting_util/) and [with the UZH CMS group](/projects/autoencodeSVJ/), I was interested in continuing to pursue research at the interface of machine learning and particle physics. 

I was very lucky to meet [University of Michigan professor Christine Aidala](http://www-personal.umich.edu/~caidala/index.html), who kindly agreed to supervise my honors thesis. I was also given the chance to contribute to some of the research projects going on within her group.

## sPHENIX hardware testing

One of the ongling projects in the group was an effort to test a number of Silicon Photomultipliers (SiPMs) for the sPHENIX detector at the RHIC. Though this process was largely automated, it also required a human operator to take shifts testing. I took a weekly shift assignment for the group.

While the work of overseeing the hardware testing process was not too intensive, I spent a lot of time in the lab discussing research projects with the graduate students in the group, which helped inform my decision to pursue PHD programs.

## ML related things

A good amount of people in the group were interested in implementing machine learning analyses, so I had quite a few very interesting conversations about different algorithms and their possible usefulness for physics.

### sPHENIX particle identification

This was a project being worked on by Dr. Sookhyun Lee & undergraduate Alan Tondryk. The goal was to determine whether machine learning might be used to improve the particle identification software for the upcoming sPHENIX experiment.

Since I had some experience in implementing machine learning for physics data analysis, I was interested in the project and met with the group weekly. My main contribution was to help with some of the syntactic quirks of implementing ML in Python, suggest algorithms I had read of that they might be able to find success with, and help debug ML-related matters. The results were written up and can be found on [Alan's research website](https://alantondryk.com/#research).

### SPS ML tutorial

I was asked by the Society of Physics Students (SPS) to host a workshop on machine learning for physics, and did so in late January 2020. [The materials can be found here](https://github.com/luclepot/SPS_ml_tutorial).

This was a two-day workshop, and I opted to make it directly interactive by using Google Colab. This meant that students could see and run code in their own Python3 environment, without the need to mess with any environmental factors.

The workshop as a whole covered

* an introduction to Jupyter notebooks & configuring Python environments by running bash commands
* an overview of data processing and loading resources
* a series of advanced visualization techniques
* an overview of ML and its uses (slide format)
* a walkthrough of building/training a simple neural network
* a small model zoo (and a particle physics example!)

It was generally well received, and generated a lot of interesting discussions afterwards!

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
