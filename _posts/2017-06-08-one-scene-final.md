---
layout: post
title:  "One-Scene-Final"
date:   2017-06-08 12:31:30 -0700
tags: [Github, jekyll]
categories: [projects]
---


# Final Documentation: One Scene
##### Group 9 - Sarah, Alice and Eric

[![youtube video](https://img.youtube.com/vi/zwdh9L1OKEc/0.jpg))](https://youtu.be/zwdh9L1OKEc)

## Concept:
Neural network system as a submissive-responsive controller of the virtual space

* “Branching” of the state based on user head movement
* Machine trying to maximize the time the user stay in the VR environment

## Model
Deep Q Learning
https://github.com/keon/deep-q-learning

Reinforcement learning in python: Theano + Keras

Source code originally written for playing CartPole game on OpenAI Gym

https://gym.openai.com/envs/CartPole-v1

![cartpole animation](https://keon.io/images/deep-q-learning/animation.gif)

“A pole is attached by an un-actuated joint to a cart, which moves along a frictionless track”

## Methods
We replaced CartPole game with our Unity VR system

#### Input
* Form: head direction (coordinate in 3d-space), head movement (acceleration data)
* Dataset: collected from a human subject - 50+ trials

#### Training
* When a human subject is bored, they push the “END” button.
* This resets the scene, the machine will retry to maximize the rewards

#### Learning
by collecting this data array:
* state 1 (VR gear readings)
* action (determined by the machine)
* state 2 (VR gear readings)
* rewards: for a unit time stay within the VR system, the system gets +1 reward; when terminated by the user, the system gets -10 penalty

#### Output
The model selected 1 action from our discrete action space (30*6*4*4*2=5760 possible actions)
which determined each object's:
* visibility,
* position,
* size (scale), and
* angular orientation

## Results

[![youtube video](https://img.youtube.com/vi/zwdh9L1OKEc/0.jpg))](https://youtu.be/zwdh9L1OKEc)

Best record?

## Contribution
* Sarah: sound + training + documentation
* Alice: python + Unity + documentation
* Eric: Unity + VR + visuals
