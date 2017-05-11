---
layout: post
title:  "Project Proposal – Generative Narrative"
date:   2017-05-01 22:09:30 -0700
tags: [proposal]
categories: [projects]
---

# Points of Interest

Narrative can take on many shapes and sizes; people who want to elevate their own work will often resort to calling themselves "storytellers" within their profession. But what does storytelling mean? How far can it be stretched? How are stories and narratives generated? 

### Questions To Explore:
  * How is narrative qualified and/or quantified?
  * Is it important to define what narrative means, especially regarding more ambiguous works?
  * What is required for the illusion of continuity / consistency?
  * Does continuity matter? How would it be measured?
  * What aspects of human-based creation and ideation are applicable or relevant?
  * Should narrative generation cater to a human audience? If not, then who?
  * How much of the human in A.I. can be removed?
  * What purpose can generated narratives serve?
  * How does this contribute to ideas around authorship?
  
### Answers We Hope to Find:
  * How a computer will parse human narratives.
  * How different narrative types are categorized.
  * What the objective & subjective results will be.
  * Whether generative narrative has a place in media / art consumption.
  
### Topics of Interest:
  * Video Editing / Cutting and Sequencing – [The Kuleshov Effect](https://www.youtube.com/watch?v=ruoPT9JeYHA)
  * Video Generation (From Noise)
  * Dialogue / Narration
  * Sound Generation
  * Artificial Existentialism
  * Generated Thought
  * Abstract Narrative

### Potential Routes / Learning Models:
  * [Unsupervised Sentiment](https://blog.openai.com/unsupervised-sentiment-neuron/)
  * Object Recognition
  * [VideoGAN](https://github.com/cvondrick/videogan)
  * T-SNE for similar video / sound / word structures
  
### Intended Outcomes:
  * To generate content of a similar variety to the data it is trained on.
  * To edit, remix, or generate narrative based on learned relationships, structures, objects.
  * To perhaps break out of the system and yield unexpected or emergent results (one can dream).

### Data:
  * Films (Classical / Auteur / Blockbuster / Foreign / etc.)
  * Screenplays
  * Novels
  * Poems
  * Tweets / Texts / Updates
  * Music
  * Speech
  * Vimeo Staff Picks
  
### Team Distribution:

The project has potential to be split up, combined, and juxtaposed in several ways:
  * By genre
  * By medium
  * By methodology  
  
No designation has been made yet.

### Success / Failure:

A human-based understanding of success / failure may focus on whether the produced content is logical, meaningful, and original. However, these are limited perspectives, and one might question whether originality can be judged, who can claim authorship, if authorship is important, and how narrative can look outside of a human environment.

### Reference Points for Further Investigation:  
  * [Benjamin, the AI that wrote _Sunspring_](http://benjamin.wtf/)
  * [Adventures in Narrated Reality](https://medium.com/artists-and-machine-intelligence/adventures-in-narrated-reality-6516ff395ba3)
  * [CharRNN](https://github.com/karpathy/char-rnn)
  * [WordRNN](https://github.com/larspars/word-rnn)
  * [PoetRNN](http://sballas8.github.io/2015/08/11/Poet-RNN.html)
  * [PixelRNN](https://github.com/tensorflow/magenta/blob/master/magenta/reviews/pixelrnn.md)
  * [SketchRNN](https://github.com/hardmaru/sketch-rnn)
  * [Neural Storyteller](https://github.com/ryankiros/neural-storyteller)
  * [Continuous Video Classification](https://medium.com/@harvitronix/continuous-video-classification-with-tensorflow-inception-and-recurrent-nets-250ba9ff6b85)
  * [Stump Speech](http://whitneyannetrettien.com/stumpspeech/)
  * [Aligning Books and Movies](http://yknzhu.wixsite.com/mbweb)
  * [Skip-Thought Vectors](https://arxiv.org/pdf/1506.06726v1.pdf)
  * [Generating Images Based on Text](https://www.digitaltrends.com/cool-tech/ai-generates-images-based-on-text/)
  * [Neural Talk Sentence Generation](http://cs.stanford.edu/people/karpathy/deepimagesent/generationdemo/)
  * [Sequence Generation](https://medium.com/artists-and-machine-intelligence/ami-residency-part-2-realtime-control-of-sequence-generation-with-recurrent-neural-network-88448dde3500)
  
### Early Proposals:

#### Routes:
  * Human writes narrative(s), machine visualizes – Human trains machine to tell stories to human.
  * Machine writes narrative(s), human visualizes – Machine trains human to tell stories to the machine.
  * Machine writes narrative(s), machine visualizes – Machine trains machine to tell stories to the machine.

#### Methods
  * Generating a text script with CharRNN for PixelRNN to generate imagery.
  * Generate music and lyrics trained on different sources.
  * Generating images through PixelRNN, then feeding them into neural storyteller to see what narrative will be produced.
  * Affecting an image via VideoGAN, then observing the changes between narratives produced by neural storyteller or some other CNN / labelling network.  
  * Create characters and allow a network to generate a story – under the ideology that "narratives" rely on characters.
  * Algorithm as its own character: self-narrating / consciousness. Trained on journal entries, or first-narrated novels.
  * Recursively training itself on its own data!!!??
