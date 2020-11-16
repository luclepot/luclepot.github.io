---
layout: page
title: coding projects
description: some side projects

img: /assets/img/pasta/porto.png
importance: 3
---

## unknownpasta

I made this to answer the age old question, *what if we could make [that one Joy Division album cover](https://www.google.com/search?q=unknown+pleasures+album+cover&tbm=isch&ved=2ahUKEwit2qy4wYbtAhUKYawKHdOODdwQ2-cCegQIABAA&oq=unknown+pleasures++albu&gs_lcp=CgNpbWcQARgAMgIIADICCAAyAggAMgIIADICCAAyAggAMgIIADICCAAyBggAEAUQHjIGCAAQBRAeOgQIABBDOgYIABAIEB46BAgAEBhQoRxY_yxg-zNoA3AAeAGAAWiIAY4FkgEDOC4xmAEAoAEBqgELZ3dzLXdpei1pbWfAAQE&sclient=img&ei=LSayX-2PHIrCsQXTnbbgDQ&bih=1231&biw=1279&rlz=1C1ONGR_enUS927US927) out of text?*

Well, [here](https://github.com/luclepot/unknownpasta) is a Python module which does just that. You input a string of text and a series of parameters, and the program outputs a joy-division-esque logo. The program generates a new logo every time, since it is based on iterative random modeling of the original.

The results:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/pasta/normal.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/pasta/porto.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/pasta/weird.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Original, text-based, and messed up. Text in the middle one is a message from a distraught friend after Brazil lost 7-1 to Germany in the world cup.  
</div>

## synefind

[this](https://github.com/luclepot/synefind) was a project a friend and I thought of a few years ago. The basic problem we wanted to solve was this:

* we liked synthesizers, especially those in the music we listened to
* we wanted to emulate voicings on our own synths / digital synths
* finding the exact combination of parameters to make a tone is *very* hard

I had several ideas for solutions, and while none panned out, it was a great learning experience. The most promising idea was to use some generative density estimation model (GAN, VAE, etc.) to learn a reversible mapping from input parameters to output waveform.

It turns out that it is very hard to effectively train generative models on synthesizer waveforms, even after transforming and processing them endlessly. The models which worked best were not good for the target purpose (backtracking to synth parameters) but they did work decently in a generative capacity. 

More importantly, the data processing yielded cool plots:

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-75" src="{{ '/assets/img/pasta/synths_cut.png' | relative_url }}" alt="" title="meeting"/>
    <div class="caption">
        time-frequency visualization of some synth waveforms
    </div>
</div>

Since first attempting this project I have gained a lot of experience working on ML projects, and I actually think this idea would be viable using a combination of more advanced (and easily convergent) techniques.

<!-- ---
layout: page
title: synefind
description: machine learning synthesizer parameters, with plugins
img: /assets/img/synefind/synths_cut.png
importance: 4
--- -->

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
