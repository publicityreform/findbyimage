---
layout: post
title: "Final Presentation – Abstraction and Composition in Machine Learning"
date: 2017-06-09 23:11:00 -0700
tags: [final presentation]
categories: [projects]
---
# Abstraction and Composition in Machine Learning
#### by Zoe, Hillary, and Vita

We spent this  quarter exploring how machine learning models can interpret and generate abstraction with images. 
Initially, we looked into style and drawing, to see what it would take to train a model to draw like we do. 

Starting with Sketch RNN, we set up a sample program that could use a set of SVG drawings to generate new drawings based on the inputs we fed it. It was successful, and worked with only 80 input images.  

![fish SVGS](http://unsolicitedairdrop.show/assets/forVita/fish1.png) 
the inputs we used

![generated fish](http://unsolicitedairdrop.show/assets/forVita/fish2.png) 
some of the fish we generated

But we were using a set of drawings that all were fish, and we quickly realized that the model program was reading different parts of the fish and mashing them together.
Thus, it wouldn't work nearly as well with abstract images and compositions, where each SVG has drastically different elements and compositions.

We did some experiments, but they all came out either as messy lines, or exact copies of one input drawing. 

We then tried DCGAN, training it on Kandinsky's paintings, to see how that might work with abstract imagery: 
<iframe src="https://www.youtube.com/embed/kU629Z3bHt0?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe>


This project is still in the works. In the future, we would like to run other abstract imageries through different models, and see if we could write our own code to generate abstract images.
Overall, the questions we are left with are mostly about what abstraction even is. Sometimes it means taking something concrete or figurative and transforming it into an correlated but wholely unrecognizable form - but does it always mean this? 
When a person makes abstract images, we feel like they are making choices with their intuition, or with some guided process. But what about when a machine creates abstract images? Then, it either feels super random, or super contrived. Is there a way around this?

Sources:
- [sketch-rnn](https://github.com/hardmaru/sketch-rnn)
- [DCGAN](https://github.com/carpedm20/DCGAN-tensorflow) 
