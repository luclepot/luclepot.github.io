---
layout: page
title: Dijet Anomaly Detection
description: Ongoing research project with Ben Nachman, in the Lawrence Berkeley National Lab ATLAS group
img: /assets/img/aad/ATLAS_anomaly_detection.png
importance: 1
---

* [**overview**](#overview)
* [**personal contributions**](#personal-contributions)
* [**algorithm and data**](#algorithm-and-datasets)
* [**reweighting results**](#reweighting-results)
* [**classification results**](#classification-results)

## overview

Machine learning is becoming an increasingly popular method of searching for new physics signals at the Large Hadron Collider. One of the most important of these searches is that for resonant new physics, in which a signal is localized to some region of the invariant mass spectrum. A classical "bump hunt" can then be performed to search for this signal in the mass spectrum, as was done to find the Higgs Boson.

In this project, we use machine learning to enhance the visibility of such bumps, using the recently proposed methods [SALAD](https://arxiv.org/ct?url=https%3A%2F%2Fdx.doi.org%2F10.1103%2FPhysRevD.101.095004&v=ee41f256) and [CWOLA](https://journals.aps.org/prd/abstract/10.1103/PhysRevD.99.014038).

## personal contributions

I joined this project full-time in the spring of 2020, with funding from the [SULI program](https://science.osti.gov/wdts/suli). My work was to analyze the performance of and extend the reach of recently developed algorithms SALAD and CWOLA with my mentor [Benjamin Nachman](http://bnachman.web.cern.ch/bnachman/), a staff scientist at LBNL.

I sought out Ben as a mentor because I had worked on & was very interested in semi-supervised ML projects for anomaly detection before. From reading various other papers and discussing with my colleagues on the CMS collaboration, I had the impression that Ben was very much a leader in the field.

Working on this project has been very exciting for me. Through a combination of previous research experience, knowledge of HEP ML techniques, and fantastic mentorship, I have been able to make consistent & unique contributions to this project. This has meant **posing & pursuing my own research questions**, **introducing & testing unique modifications** to algorithm routines, and **preparing & presenting** talks and papers on this work for conferences and ATLAS internal meetings. This experience has made me excited to start work in a PHD program, and reinforced my desire to pursue a career in particle physics research.


Day-to-day research tasks

* Re-implementing them and verifying their initial results
* Applying SALAD to ATLAS group data
* Checking SALAD's response to data correlations
* Quantifying SALAD's ability to estimate the signal-region background across a number of plausible signals
* Synthesizing this information in the form of a concrete analysis plan

All of these tasks are implemented in Python, using Keras/Tensorflow for the machine learning, and run on the [NERSC's CORI supercomputer](https://www.nersc.gov/news-publications/nersc-news/nersc-center-news/2016/cori-supercomputer-now-fully-installed-at-berkeley-lab/). This work served the purpose of clarifying the performance of SALAD, working out several bugs and workarounds in its implementation, and preparing it for large-scale application to ATLAS group data in a dedicated search.

A paper on our work since this spring has been **accepted to the 2020 NeurIPS conference** (Machine Learning for the Physical Sciences workshop), which I will be presenting. This work has also been [**submitted for review**](https://arxiv.org/abs/2009.02205) to a particle physics journal.

**A majority of the results from this project cannot be displayed here, since they are internal to the ATLAS group.** If you are an ATLAS group member and would like to see more, please [contact me](mailto:luclepot@umich.edu). For all of the following plots, I use the [**Pythia and Herwig based simulations from the 2020 LHC Olympics**](https://indico.cern.ch/event/809820/page/16782-lhcolympics2020-rd).


## algorithm and datasets

The most basic version of SALAD (Simulation Assisted Likelihood-free Anomaly Detection) proceeds as follows:

1. Choose a set of features $$m$$ which localize a possible signal into a signal region $$R_\text{signal}$$ (where the signal might be more plentiful), and a sideband region $$R_\text{sideband}$$. Choose additionally a set of discriminating features $$x$$.

2. Generate both a real dataset and a decent simulation with these features. 

3. Train a classifier $$f(x, m)$$ to distinguish between data and simulation for $$m \in R_\text{sideband}$$.

4. Reweight the simulation using $$f(x,m)$$ according to the [DCTR](https://arxiv.org/abs/1907.08209) procedure, with weights given by
    
    $$w(x | m) = \frac{f(x, m)}{1 - f(x, m)}$$

5. Train a second classifier $$g(x)$$ to distinguish reweighted simulation and data for $$m\in R_\text{signal}$$.

<div class="col justify-content-sm-center">
    <img class="mx-auto rounded d-block z-depth-1 w-65" src="{{ '/assets/img/aad/SALAD_arch.png' | relative_url }}" alt="" title="SALAD architecture"/>
    <div class="caption">
        SALAD architecture
    </div>
</div>

This algorithm is **semi-supervised**, and can have varying degrees of signal-model independence. Signal model independence generally decreases as the set of localizing features $$m$$ increases; in the limit of many features $$m$$, we basically just have a standard HEP bump hunt analysis.

Since ATLAS data is not available publicly, I'll use the fully simulated LHCO data described above to show my results, taking the Pythia simulation to be "data" and the Herwig simulation to be "Simulation." Since they are fundamentally different, this provides a good test case for our algorithms.

We opt to search for a common signal, of the form $$Z \rightarrow X,Y$$, where $$X$$, $$Y$$, $$Z$$ are all bosons and $$Z$$ is some hypothetical new particle. This is a dijet resonance, and the signal is resonant (and thus may be localized) in invariant dijet mass $$m_{JJ}$$. For testing, we used a Pythia signal simulation where $$Z$$ is a hypothetical 3.5 TeV $$W^\prime$$ boson.

We then choose a signal region width (500 GeV, in this case) and slide it across the $$m_{JJ}$$ spectrum, training models and searching for signal patterns at each place. For testing and computational convenience, we show results for a signal region centered on the peak of the $$W^\prime$$ resonance:

<div class="col justify-content-sm-center">
    <img class="w-75 img-fluid mx-auto rounded d-block z-depth-1" src="{{ '/assets/img/aad/SALAD1_mjj_prezi_0630-1.png' | relative_url }}" alt="" title="Pythia/Herwig Signal/Sideband Regions"/>
    <div class="caption">
        signal and sideband regions for pythia "data", herwig "simulation", and pythia "signal"
    </div>
</div>

Though I added many more features with the ATLAS dataset, this dataset was limited to the jet masses and $$n$$-subjettiness ratios $$\tau_{21}$$ and $$\tau_{32}$$, though this is still an improvement from earlier iterations. The features are shown below; note that in features other than $$m_{JJ}$$, the Pythia and Herwig simulations exhibit significant differences.

<div class="col justify-content-sm-center">
    <img class="w-100 img-fluid mx-auto rounded d-block z-depth-1" src="{{ '/assets/img/aad/features.png' | relative_url }}" alt="" title="feature plots"/>
    <div class="caption">
        Full feature plots, with histogram ratios
    </div>
</div>

## reweighting results

The reweighting in step 4 can be verified visually, and with a variety of distribution similarity tests. A typical example of these results are shown below for a very high signal to background ratio ($$S/B$$).

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/aad/ATLAS_anomaly_detection.png' | relative_url }}" alt="" title="node reweightings"/>
    </div>
    <div class="col-sm-7 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/aad/reweighting_results.png' | relative_url }}" alt="" title="reweightings"/>
    </div>
</div>
<div class="caption">
    Original and reweighted distributions for the NN output (left) and discriminating features (right)
</div>

It is obvious from the "Pythia/Herwig" ratio plots that the reweighted distribution, shown in green, are a much better match to the "data" than the non-reweighted distributions. 


## classification results

Here I will show a few of the performance tests I performed. This is only a very small subset, since I am not able to share ATLAS internal data/documents. However, even these tests are interesting.

First, we can show SALAD's discovery potential over a range of $$S/B$$ ratios, with no modifications. It is clear that the performance is quite good, even at fairly low ratios:

convenience, we show results for a signal region centered on the peak of the $$W^\prime$$ resonance:

<div class="col justify-content-sm-center">
    <img class="w-100 img-fluid mx-auto rounded d-block z-depth-1" src="{{ '/assets/img/aad/salad_reg.png' | relative_url }}" alt="" title="Regular SALAD Results"/>
    <div class="caption">
        ROC and relative significance curves for SALAD on LHCO data
    </div>
</div>

Next, we can verify SALAD's robustness to correlated inputs by inducing a strong correlation between jet mass and $$m_{JJ}$$. This is done by modifying the jet masses such that $$m_J \rightarrow m_J + 0.1\cdot m_{JJ}$$ for each jet mass $$m_J$$. These results are shown as well 

<div class="col justify-content-sm-center">
    <img class="w-100 img-fluid mx-auto rounded d-block z-depth-1" src="{{ '/assets/img/aad/salad_shift.png' | relative_url }}" alt="" title="Correlated SALAD Results"/>
    <div class="caption">
        ROC and relative significance curves for SALAD on LHCO data with induced correlations
    </div>
</div>

We see that performance is comprable, with a boost in performance in the low $$S/B$$ region. Either way, it is clear that SALAD is robust to even very strong correlations. 

We can also plot metrics such as the AUC and maximum relative significance $$\epsilon_S/\sqrt{\epsilon_B}$$ for these models to compare them more directly. Here we plot the median and IQR of 20 models trained at each point:

<div class="col justify-content-sm-center">
    <img class="w-75 img-fluid mx-auto rounded d-block z-depth-1" src="{{ '/assets/img/aad/salad_corr_results.png' | relative_url }}" alt="" title="metric plots"/>
    <div class="caption">
        AUC and maximum relative significance plots for SALAD on both normal and correlated LHCO data
    </div>
</div>

We see from these plots that the performance of SALAD on this test dataset is both quite good, and robust to correlations between resonant and discriminating features.

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
