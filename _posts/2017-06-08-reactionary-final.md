---
layout: post
title:  "reactionary"
date:   2017-06-08 13:13:30 -0700
tags: [Github, jekyll]
categories: [projects]
---


# reactionary
##### stalgia

## Concept:
Create a machine-defined relationship between observed contant and human facial response using Youtube 'reaction videos'. Use this model to create new facial reactions for content that I create and compile it into a single looping video. There is an inherent performativity to the 'reaction video' format which exposes the social utility of the reaction which is to express a relative and categorizable ethical framework. This points to a tendency to integrate the exterior image into our understanding of our own relative righteousness.

## Tools
[Pix2Pix](https://github.com/phillipi/pix2pix)
cGAN using Torch and Lua

[Neural Enhance](https://github.com/alexjc/neural-enhance)
CNN using Tensorflow and Python

## Methods
After several failed attempts to adapt [Deep Multi-Scale Video Prediction](https://github.com/dyelax/Adversarial_Video_Generation) to my needs. I turned to Pix2Pix.

Trained Pix2Pix on dataset, made new videos and used those to generate new reaction faces, these new videos were enlarged with Neural Enhance

## Datasets
2400 pngs taken from 40 different youtube reaction videos. 3 out of 4 of each videos frames were dropped and one second at 30 fps was taken out of the resulting reaction and source video.

## Training
Trained six different times with slight changes to the dataset between each training. Models were trained on a Google Cloud computer with 32 vCPUS and 128 GB of RAM. Training took roughly 3 days for each model.

![image of training progress](/findbyimage/assets/stalgia_training_image.png)

## Output
I made a series of videos and then generated reactions to them using the model. The final results were composed into a single-channel looping video piece along with a stream-of-consciousness text that I wrote that addresses several of the themes.

## Final Piece

[reactionary](https://drive.google.com/file/d/0B4v9wGHsYuR2WEQwZ2xwR1dIS0k/view?usp=sharing)

## Texts Used
[Deep multi-scale video prediction beyond mean square error](https://arxiv.org/abs/1511.05440)
[Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network](https://arxiv.org/abs/1609.04802)
[Image-to-Image Translation with Conditional Adversarial Networks](https://arxiv.org/pdf/1611.07004v1.pdf)

