---
layout: post
title: "Final Presentation – Generative Narrative"
date: 2017-06-05 23:11:00 -0700
tags: [final presentation]
categories: [projects]
---

# Generative Narrative
by Tyler Yin, Reginald Lin, Annie Yu  

To explore how machine learning might be used to generate narratives in the context of art-making, we experimented with several different neural networks to produce stories in the form of text and moving imagery. 




### Resources
#### Text-based Models:
  - Char-RNN, a multi-layer RNN with long short-term memory that generates character-level text
  - Torch-RNN, a high-performance, reusable RNN, similar to Char-RNN
  - Neural Storyteller, a model that analyzes an image and produces a story
  - Word-RNN (tensorflow), similar to Char-RNN but uses pre-trained word vectors  
  
#### Image-based Models:
  - ConvNetJS – Image Painting, a CNN used to predict pixel colors of an image
  - Butterflow, for motion interpolation / smoothing / fluid slow motion videos  


### Links  
For more context on this project, go to these iterations:
  - [Project Proposal](https://publicityreform.github.io/findbyimage/generative-narrative-project-proposal.html)
  - [Proof-of-Concept](https://publicityreform.github.io/findbyimage/generative-narrative-proof-of-concept.html)
  
  
### Training Data  
In order to avoid simply trying to emulate a singular work or author, we compiled text from a variety of sources, including novels written by Haruki Murakami, Joseph Conrad, and Albert Camus. We wanted to focus on works written by authors interested in the human condition, given to introspection, and generally writing in first-person perspective. For access to the text used for training and sampling, refer [here](assets/a-r-t-folder/fpn.txt).


### Process
#### Word-RNN
Using the tensorflow version of Word-RNN, we sampled for text during different checkpoints to track the progress of the model, keeping primetext and other hyperparameters consistent. After the model was finished training, text was generated and used for priming another generation, which was used for priming another generation...and so on, for seven cycles / chains.

#### ConvNetJS – Image Painting 
![A screencapture of the original image next to the generated image](assets/a-r-t-folder/5.PNG)  
In an attempt to produce abstracted videos, we uploaded source images based on some of the generated texts to an image learning neural net and generated frames individually. Each frame was selected for its ability to stand alone, then 6-10 were compiled into a .gif, later converted into an .mp4 for experiments with butterflow.

#### Butterflow
We processed our results with butterflow, in an attempt to exploit and discover latent space interpolation. Butterflow renders intermediate frames between existing frames using motion interpolation. The most successful and desirable usage of BF was interpolating with few source frames for "time-lapse" videos. 


### Results  
#### Painted Narrative  
![A moving abstraction generated from ConvNetJS](assets/a-r-t-folder/n1.gif)
![A moving abstraction generated from ConvNetJS](assets/a-r-t-folder/n2.gif)
![A moving abstraction generated from ConvNetJS](assets/a-r-t-folder/n3_1.gif)
![A moving abstraction generated from ConvNetJS](assets/a-r-t-folder/n4.gif)


#### Written Narrative  
Curation of passages from original chain of text, produced by Word-RNN:  
![A page of written text generated from Word-RNN](assets/a-r-t-folder/editingWordRNN.png)   
Excerpts:  
  - "In other words, I learned about what isn't. But she was such serious pain. My heart would throb."
  - "I have experienced no moral obligations."
  - "Can your shadow come back here? I same some place. In this Town, the Gatekeeper will bring the seat for full men in a race about those things."
  - "Fine, he said. He had his reason for his purpose with her studies, of this violent channel, the girls who were started constantly in the world of interest."
  - "She could hear the touch of Tengo's consciousness, a huge, shot recorder and the occasional night-transport truck."

#### Interpolated Narrative  
<iframe src="https://player.vimeo.com/video/220438705?title=0&byline=0&portrait=0" width="640" height="369" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
By interpolating between samples from different checkpoints to obfuscate the text on a visual and surface level, we intended to bring attention to the algorithmic nature of the constructed narrative. 


### Issues  
  - Neural Storyteller was ideal for the purposes of the project, but skip-thought vectors was too difficult to get working
  - Focusing on just skip-thought vectors through tensorflow yielded similar results: nothing
  - Training data could have been more adequately diverse, such that there would be an even distribution of text from original authors  
  - Training the model lasted approximately 12 hours
  - After 49 epochs with Word-RNN, training loss = 2.687


### Footnotes
  - [Word-RNN-Tensorflow](https://github.com/hunkim/word-rnn-tensorflow)
  - [ConvNetJS](http://cs.stanford.edu/people/karpathy/convnetjs/demo/image_regression.html) 
  - [Butterflow](https://github.com/dthpham/butterflow)
  - [Andrej Karpathy](http://cs.stanford.edu/people/karpathy/)
