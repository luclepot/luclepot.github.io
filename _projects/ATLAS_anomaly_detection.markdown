---
layout: page
title: Dijet Anomaly Detection
description: Ongoing research project with Ben Nachman, in the Lawrence Berkeley National Lab ATLAS group
img: /assets/img/aad/ATLAS_anomaly_detection.png
importance: 1
---

**Contents**

* [overview](#overview)
* [personal contributions](#personal-contributions)

## overview

Machine learning is becoming an increasingly popular method of searching for new physics signals at the Large Hadron Collider. One of the most important of these searches is that for resonant new physics, in which a signal is localized to some region of the invariant mass spectrum. A classical "bump hunt" can then be performed to search for this signal in the mass spectrum, as was done to find the Higgs Boson.

In this project, we use machine learning to enhance the visibility of such bumps, using the recently proposed methods [SALAD](https://arxiv.org/ct?url=https%3A%2F%2Fdx.doi.org%2F10.1103%2FPhysRevD.101.095004&v=ee41f256) and [CWOLA](https://journals.aps.org/prd/abstract/10.1103/PhysRevD.99.014038).

## personal contributions

I joined this project along with Kees Benkendorfer in the spring of 2020, with funding from the [SULI program](https://science.osti.gov/wdts/suli). My work concerned taking the SALAD and CWOLA algorithms -- methods recently developed by my mentor, Ben Nachman -- and test them rigorously. This included

* Reimplementing them and verifying their initial results
* Applying SALAD to real ATLAS group data
* Checking SALAD's response to data correlations
* Quantifying SALAD's ability to estimate the signal-region background

All of these tasks are implemented in Python, using Keras/Tensorflow for the machine learning. This work served the purpose of clarifying the performance of SALAD, working out several bugs and workarounds in its implementation, and preparing it for large-scale application to ATLAS group data in a dedicated search.

A paper on our work since this Spring has been accepted to the 2020 NeurIPS conference (Machine Learning for the Physical Sciences workshop), which I will be presenting. This work has also been [submitted to the journal PRD](https://arxiv.org/abs/2009.02205) for review.

A majority of the results from this project cannot be displayed here, since they are internal to the ATLAS group. For all of the following plots, I use the [**Pythia and Herwig based simulations from the 2020 LHC Olympics**](https://indico.cern.ch/event/809820/page/16782-lhcolympics2020-rd).


## analysis

### the SALAD algorithm



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
