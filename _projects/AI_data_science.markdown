---
layout: page
title: student achievement gap analyses
description: Ongoing data science fellowship with the University of Michigan Center for Academic Innovation

img: /assets/img/ai/umai_plot.jpg
importance: 2
---

## hiring process

In the spring of 2019, I was interested in different ways of collecting data online, mostly using Python. I developed a number of web scraping projects, with focus ranging from flight data to college course statistics.

In one such project, I collected data provided by the UM Center for Academic Innovation regarding course evaluations. I did so because while the [website on which the data was hosted](https://atlas.ai.umich.edu/) provided some intuition of the data, I was interested in making my own visualizations comparing many courses in aggregate. Unfortunately, my code had a bad interaction with the website's database, causing it to crash multiple times and my umich account to be suspended.

I was contacted by an administrator who at first reprimanded me, and then asked what I was using the data for in the first place. I showed him some of my plots and he suggested that I apply to work officially with him as a data science fellow, through the [**University of Michigan's Center for Academic Innovation**](https://ai.umich.edu/) (CAI). I began working in the fall of 2019.

## personal contributions

As a data science fellow, I work in collaboration with a number of data scientists, school administrators, and sociology professors. My main focus is to quantify and explain the effect (or lack thereof) of the online learning tools provided by CAI on student performance. **I am particularly interested in learning more about the way that the "helpfulness" of such tools changes based on student demographics such as race, gender identification, and family income.** I believe that these questions are key to better understanding how institutions such as the University of Michigan can adapt themselves to better accommodate underserved communities.

Since this data is highly sensitive, I am by federal law unable to share it (or any visualizations I make of it) publicly. However, I can talk about some of the non-specifics of the work I do, and go over an analysis I was asked to do as a part of my application.

### work details

**The analysis I am currently working on focuses on the impact of the [ATLAS tool](https://atlas.ai.umich.edu/) on student performance, and how this tool either alleviates or worsens disparities in student performance along demographic lines**. Much of this work is done in collaboration with a professor of sociology at the University of Michigan.

Day-to-day work consists mainly of

* processing and cleaning large (100 gb) files of student course, demographic, & enrollment information
* meeting with administrative and sociologist coworkers to discuss our current understanding and develop specific research questions to pursue
* designing Python visualizations which provide precise answers (or at least add clarification) to these research questions

### application analysis

This analysis was a part of my application for the fellowship. The actual analysis part is viewable [in full on my github](https://github.com/luclepot/recent_grad_analysis), or more legibly as a [**pre-rendered jupyter notebook**](https://nbviewer.jupyter.org/github/luclepot/recent_grad_analysis/blob/master/analysis.ipynb). This analysis gives a (greatly simplified) example of the kind of work I might be asked to do in the fellowship, as well as the visualization/documentation styles I might use. I'll give an overview here.

The application asked me to analyze [college major data from FiveThirtyEight](https://github.com/fivethirtyeight/data/tree/master/college-majors) **in two hours**. In the analysis, I walk the reader through

* cleaning and verifying the datasets
* my plotting/visualization logic
* possible future steps with the dataset, given more time

I made three plots of the data. One visualizes the **absolute current unemployment rates over a variety of majors and major groupings**:

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-100" src="{{ '/assets/img/ai/unemployment_rate.png' | relative_url }}" alt="" title="unemployment rates"/>
    <div class="caption">
        unemployment rate viz
    </div>
</div>

The second visualizes the **change in unemployment rate** between all college graduates and "recent" college graduates, as defined by FiveThirtyEight:

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-100" src="{{ '/assets/img/ai/ue_rate_change.png' | relative_url }}" alt="" title="most/least booming majors"/>
    <div class="caption">
        unemployment rate increase viz
    </div>
</div>

The last visualizes the **most/least booming majors**, defined by the size of their increase/decreases in employment, respectively:

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-100" src="{{ '/assets/img/ai/booming_majors.png' | relative_url }}" alt="" title="most/least booming majors"/>
    <div class="caption">
        most/least booming major viz
    </div>
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
