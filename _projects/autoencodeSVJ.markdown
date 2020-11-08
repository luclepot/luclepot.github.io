---
layout: page
title: Autoencoders for Semi-Visible Jet Detection
description: Ongoing research project with the University of Zurich CMS Group
img: /assets/img/autoencodeSVJ.png
importance: 2
---

## overview

[Semi-visible jets](https://arxiv.org/abs/1503.00009) are a promising explanation for both the **missing transverse momenta** in proton-proton collisions at the LHC and for the **nature and origin of Dark Matter**. This theory admits new "dark sector" particles; however, such particles have a wide range of unconstrained parameters. Since dedicated searches across this large phase space can be impractical, we present here an **unsupervised method for Semi-Visible jet detection, using neural autoencoders.**

## personal involvement

I recieved funding for this project from both the [University of Michigan International Institute](https://ii.umich.edu/) and the [Swiss Office of Science](https://thinkswiss.org/research-scholarship/). I lived in Geneva, Switzerland and worked at CERN during the Summer of 2019.

While the idea of using neural autoencoders for this analysis was sparked by conversations with Annapaola de Cosa and Maurizio Pierini, I am the sole author of all work involved in this analysis. This includes
* a ROOT C++ based data selection chain
* a high-performance Python data processing chain
* simultaneous Autoencoder training and testing frameworks, written in Python with Keras/Tensorflow
* Python analysis and plotting of results

The code for this repository is given [here](https://github.com/luclepot/autoencodeSVJ); all code, plots, and results shown here are my work.

## analysis

In the case we investigate for this analysis, we consider a hypothetical dark sector W-boson <img src="https://render.githubusercontent.com/render/math?math=W^\prime">. For this particle, the chief unconstrained parameters are

1. the fraction of dark sector particles decaying back to the Standard Model <img src="https://render.githubusercontent.com/render/math?math=r_{\text{inv}}"> and
2. the mass of the <img src="https://render.githubusercontent.com/render/math?math=W^{\prime}"> boson

Rather than deploy an ensemble of searches across a grid of possible combinations - as might be done in a traditional analysis - we make use of a neural autoencoder to estimate the QCD background in an unsupervised manner. We then evaluate this autoencoder over a wide range of signal parameters, and show that **the autoencoder has excellent signal discovery across a range of signal parameters.**

The architecture of the autoencoders used in this analysis is shown below.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/autoencodeSVJ.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<!-- 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SVJ/best_ae_aucs10p_average.png' | relative_url }}" alt="" title="example image"/>
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
 -->
<div class="caption">
    Autoencoder architecture for this analysis
</div>


The input and reconstructions distributions of the data are shown below. These include a set of Energy Flow Polynomials, which form a basis for describing jet substructure. We see from these distributions that in general, the reconstructions of SVJ signal are worse than the reconstructions of QCD background, implying that we will see some performance increase.

Also shown are the reconstruction error distributions, which parameterize the total error across all features. As expected, we see that these are significantly higher in general than for the SVJ than the QCD.

<div class="row justify-content-sm-center">
    <div class="col-sm-7 mt-4 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SVJ/reconstruction_plot.png' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-5 mt-4 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SVJ/errors_recon_all.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>

<div class="caption">
    Input and reconstructed variable distributions (left) and mean squared reconstruction error distributions (right) for one of the selected autoencoders.
</div>

Lastly, we show the relative significance increases and S/B ratios across a cut on the autoencoder MSE betweeen inputs and reconstructions. By observation, significance increases are ~6 in the maximum range, indicating good discovery.

<div class="row">
    <div class="col-sm mt-2 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/SVJ/sb_ratios_relsigs.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Signal-to-background ratios and relative significance plots
</div>

<!-- The code is simple.
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
