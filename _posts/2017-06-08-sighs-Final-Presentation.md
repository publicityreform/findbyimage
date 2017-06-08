---
layout: post
title:  "Sighs Final Presentation"
date:   2017-06-07 
tags: [final presentation]
categories: [projects]
---

# sighs
by Chelly Jin, Jack Turpin, and Youjin Chung

An exploration on how the analysis and application of nonverbal communication in computers possibly illuminate different perspectives in human/computer interfaces.

## Collecting Data
We provided a list of 6 characterisitcs and prompted each person to sigh in a manner that they felt best identified or characterized these words.
### The Characteristics 
* dismay
* dissatisfaction
* boredom
* futility
* relief
* love lorn

We collected data from friends and acquaintances; however, a good portion of our data came from our Mechanical Turk Request.
Our parameters in the Mechanical Turk Request: 

![Mechanical Turk Parameters Image](http://diversity.p5js.org/sigh.png)

* [Listen to some of the crowdsourced sighs here](https://vimeo.com//220874421)

## Define
1. Open Frameworks to retrieve the audio data.

2. Wekinator to train the model 
Utilized wekinator to record the audios to train the model. 
![Image of Wekinator and Data Training](http://diversity.p5js.org/sighs6.png) 

3. Processing to showcase the output. 
![Image of Processing output](http://diversity.p5js.org/sighs5.png) 


## Generate
Utilized Word2Vec and t-SNE Word embeddings. 
When given a word, it links the word to the closest characteristic (dismay, dissatisfaction, boredom, futility, relief, love lorn) and plays an audio snippets of the respective characteristic. 

![word2vec jupyter image](http://diversity.p5js.org/sigh1.png)
![word2vec jupyter image](http://diversity.p5js.org/sigh2.png)
![word2vec jupyter image](http://diversity.p5js.org/sigh3.png)
![word2vec jupyter image](http://diversity.p5js.org/sigh4.png)
![word2vec jupyter image](http://diversity.p5js.org/sigh7.png)

## Footnotes

* [Open Frameworks](http://openframeworks.cc)
* [Wekinator](http://www.wekinator.org)
* [Processing](https://processing.org)
* [Word2Vec](https://www.tensorflow.org/tutorials/word2vec)


