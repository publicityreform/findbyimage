---
layout: post
title:  "latent space"
date:   2017-05-23 01:52:15 -0700
tags: [latent space]
categories: [Notes]
---

http://www.evolvingai.org/ppgn

http://vdumoulin.github.io/morphing_faces/online_demo.html


a super-interesting article from google’s magenta working group on using neural networks to synthesize (musical) audio: [https://magenta.tensorflow.org/nsynth-instrument](https://magenta.tensorflow.org/nsynth-instrument)

and this maybe even more interesting article (and corresponding [twitter-bot](https://twitter.com/smilevector) about [traversing latent space in images](https://arxiv.org/pdf/1609.04468.pdf) (see how to remove a smile from a face using SLERP (spherical linear interpolation), for instance)


using magenta’s port of sketch-rnn (in jupyter notebook)

install magenta environment (a toolkit built on top of tensorflow, specifically for “creative” tasks) following the instructions [here](https://github.com/tensorflow/magenta)

if you’ve already set up a cloud compute instance that includes anaconda, you can follow these steps:

type `curl https://raw.githubusercontent.com/tensorflow/magenta/master/magenta/tools/magenta-install.sh > /tmp/magenta-install.sh
bash /tmp/magenta-install.sh` into terminal at the prompt

`conda create -n magenta python=2.7 jupyter
source activate magenta`

`pip install magenta`

alternatively, you can launch [the magenta docker container](https://github.com/tensorflow/magenta#docker) 

if you are interested, read [this thorough high-level talk](https://medium.com/artists-and-machine-intelligence/a-journey-through-multiple-dimensions-and-transformations-in-space-the-final-frontier-d8435d81ca51) by memo atken on the importance of dimensional spaces in machine learning:

