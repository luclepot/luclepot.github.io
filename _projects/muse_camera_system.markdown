---
layout: page
title: liquid H2 target fabrication & monitoring
description: 2 year research project with Prof. Wolfgang Lorenzon, in the University of Michigan MUSE Group
img: /assets/img/muse/muse_cam.jpg
importance: 4
---

* [**overview**](#overview)
* [**personal contributions**](#personal-contributions)
    * [**hardware work**](#hardware-work)
    * [**computer vision camera system**](#camera-system)

## overview

I began working on this project in January 2017, during my freshman year of college. I continued to contribute, in both a full- and part-time capacity, until January 2019.

I worked for Wolfgang Lorenzon's MUon Scattering Experiment (MUSE) group, which focused on constructing the liquid hydrogen target for the MUSE experiment. The MUSE experiment as a whole aims to provide more information (or a resolution) to the [proton radius puzzle](https://www.nature.com/articles/d41586-019-03364-z) by making simultaneous electron-proton and muon-proton scattering measurements of the proton radius. No muon-proton scattering measurement has been made yet, so the commencement of data collection (planned for early 2021) is eagerly awaited.

## personal contributions

As mentioned before, I worked for this group for about two years. For the last year or so, I served as a mentor for newer undergraduate students, giving them tasks to help with (mostly on the codebase discussed later).

My work with the MUSE group at the University of Michigan resulted in a presentation [at the 2017 APS DNP meeting](https://ui.adsabs.harvard.edu/abs/2017APS..DNP.EA063L/abstract), as well as a [paper on the finished liquid hydrogen target](https://linkinghub.elsevier.com/retrieve/pii/S0168900219312963).

### hardware work

A large part of my work was hardware-based. Along with the lab's post-doc, Priyashree Roy, I contributed directly to the design, fabrication, and testing processes for the liquid hydrogen target used in the MUSE experiment. In particular, I was in charge a majority of the machining, blowtorch welding, and assembly for the target prototypes. This included machining and construction of prototypes for the

* Kapton target cells
* Copper target endcaps
* Copper support tubes & VCR fittings
* Copper fill/exhaust pipe 

These components are shown in the target ladder schematic below. In addition to fabrication, I worked closely with Dr. Roy to rigorously test the designs at both low temperature and high pressures. This work involved pressurizing target cells with helium gas, submerging them in liquid nitrogen, and testing multiple cell prototypes to failure. This work contributed significantly to the final target ladder design, as we changed the design of the target ladder support system and target cells according to information gained from the tests.

<div class="row">
    <div class="col-sm mt-6 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/muse/target_ladder.png' | relative_url }}" alt="" title="ladder schematic"/>
    </div>
    <div class="col-sm mt-6 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/muse/ladders.jpg' | relative_url }}" alt="" title="finished ladders"/>
    </div>
</div>
<div class="caption">
    MUSE target ladder schematic (left) & finished set of ladders (right)
</div>


### camera system

This project is my main contribution to Dr. Lorenzon's research group. After working in the group for awhile, I was asked to design a position monitoring system for the target ladder. This is necessary because the target ladder (shown above) **has the potential to move significantly during the filling/venting of liquid hydrogen** from the target cells. 

<img class="img-fluid rounded z-depth-1" width="25%" align="right" src="{{ '/assets/img/muse/target_chamber.png' | relative_url }}">

Since the target ladder is anchored only from the top, the heating and cooling of copper components in the ladder can cause them to expand or contract. Such movement might cause a tilt or shift in the axis of the target ladder, introducing an unnecessary source of error.

The target ladder is housed in a vacuum sealed target chamber, shown at right. Due to detectors and other machinery, the space for this position monitoring system was limited to the area below the target, underneath the target chamber.

Using Python and the computer vision framework [OpenCV](https://opencv.org/), **I was the sole author of a windows native program which determines the 3-dimensional shift of the target ladder from its initial axis**. [The repository for this code is here](https://bitbucket.org/luclepot/muse_camera_system/src/master/).

I was responsible for both the hardware and software of the project, which was successfully completed and is now implemented as a part of the experimental routine. This project took about 1.5 years, with some variation in the amount of work I was able to contribute every week. The development of this project involved, among other things, 

* a detailed **mathematical analysis of target & computer vision geometry**/implementation & verification in code 
* **designing a data management framework** for the high volume of computer vision data, including positional measurements and calibrations
* **determining & programming an optimal calibration routine**, for both the camera and target ladder
* performing a number of experiments to **determine the optimal computer-vision camera, lens, and filter for the purpose of this system**, and commissioning its purchase
* writing **python wrappers for hardware drivers** written in C and C++ in order to use our camera
* writing a **native windows GUI program** to run position monitoring & calibration routines for general use/users with no programming expertise
* **designing and machining an aluminum camera mount**, including a custom threading matching that of the camera's filter threads. Also involved testing/purchasing an LED lighting system

Below are some photos and explanations of some of my work. 

<div class="row">
    <div class="col-sm-7 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/muse/mount.png' | relative_url }}" alt="" title="camera mount schematic"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/muse/muse_cam.jpg' | relative_url }}" alt="" title="finished camera mount"/>
    </div>
</div>
<div class="caption">
    CAD drawing and resultant camera mounting plate, with LED light & attached camera
</div>

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-100" src="{{ '/assets/img/muse/targets.jpg' | relative_url }}" alt="" title="test targets"/>
    <div class="caption">
        Testing the computer vision system target identification, with identified target rings/centers drawn in red
    </div>
</div>

<div class="row">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/muse/gui_sc.png' | relative_url }}" alt="" title="screenshot of GUI software"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/muse/unnamed.jpg' | relative_url }}" alt="" title="camera & LED in action"/>
    </div>
</div>
<div class="caption">
    Early iteration of Windows GUI measurement view (left) and testing the finished camera mount schematic (right)
</div>

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
