---
layout: post
title:  "Day 11 In-class Notes"
date:   2017-05-09 21:52:15 -0700
tags: [RNN]
categories: [Notes]
---

most RNN’s belong to the general category of “generative” models, in that these models provide a departure from strict classification or prediction tasks. it's important to remember, though, that even generative _models_ still tell us alot about how we project rational thought onto the world, and depend greatly on how our design, contextualization, objectives, and choice of training data!

for a loose narrative of using RNN's for artistic purposes see [ross goodwin _”adventures in narrated reality”_](https://medium.com/artists-and-machine-intelligence/adventures-in-narrated-reality-6516ff395ba3) - see also [_"Sunspring"_ the movie he made with RNN-generated script](https://arstechnica.co.uk/the-multiverse/2016/06/sunspring-movie-watch-written-by-ai-details-interview/)

allison parrish: “When we teach computers to write, the computers don’t replace us any more than pianos replace pianists—in a certain way, they become our pens, and we become more than writers. We become writers of writers.”

some thoughts on exploring semantic space with experimental writing from [Allison Parrish](http://opentranscripts.org/transcript/semantic-space-literal-robots/), and these [two](https://medium.com/@katierosepipkin/a-long-history-of-generated-poetics-cutups-from-dickinson-to-melitzah-fce498083233) [posts](https://medium.com/@katierosepipkin/language-after-the-writing-machine-f3bff4f73408) from katie rose pipkin (see also their [moth generator twitter bot](https://twitter.com/mothgenerator))

for technical background on RNN's:
* [intro to RNN’s from andrej karpathy](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)
* [intro to RNN’s from “machine learning is fun”](https://medium.com/@ageitgey/machine-learning-is-fun-part-2-a26a10b68df3)
* [intro to RNN’s from wildML](http://www.wildml.com/2015/09/recurrent-neural-networks-tutorial-part-1-introduction-to-rnns/)
* [intro to RNN’s from chris olah](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) (chinese translation [here](http://www.jianshu.com/p/9dc9f41f0b29))
* [collection of many resources related to learning about RNN’s](https://handong1587.github.io/deep_learning/2015/10/09/rnn-and-lstm.html)
* [attention and memory](http://www.wildml.com/2016/01/attention-and-memory-in-deep-learning-and-nlp/)
* [augmented RNN’s (more on attention and memory)](http://distill.pub/2016/augmented-rnns/)

[compared](http://nbviewer.jupyter.org/gist/yoavg/d76121dfde2618422139) to maximum-likelihood language models (e.g. Markov chains), RNN’s manage to balance structure at different scales (context-awareness) while generating completely new material (no copying).

[compared](https://metamind.io/research/learning-when-to-skim-and-when-to-read) to using other natural langauge processing tools on their own (like "bag-of-words"), RNN's in general, and LTSM's in particular, help keep track of overall sentiment or longer arcs.


some projects using RNN's:
* [generating click-bait news stories](http://clickotron.com/about)
* [bot based on a collection of one human's communications](https://www.theverge.com/a/luka-artificial-intelligence-memorial-roman-mazurenko-bot)
* [musical compositions (with interesting repetitive features!)](http://www.hexahedria.com/2015/08/03/composing-music-with-recurrent-neural-networks/)
* [generating new choreography from existing dances](http://peltarion.com/creative-ai) suggests the possibility of [using RNN’s to parse the relationship between points in space](https://twitter.com/evolvingstuff/status/713149843481317376) aka [structured feature learning](https://twitter.com/alexjc/status/716549734371102720/photo/1)
* [memo atken's realtime sequence generator / style shifter](https://medium.com/artists-and-machine-intelligence/ami-residency-part-2-realtime-control-of-sequence-generation-with-recurrent-neural-network-88448dde3500)
* [_”recurrent net dreams up fake chinese characters”_ from otoro blog](http://blog.otoro.net/2015/12/28/recurrent-net-dreams-up-fake-chinese-characters-in-vector-format-with-tensorflow/)
* [a neural representation of sketch drawings](https://arxiv.org/pdf/1704.03477.pdf)

some code repositories of RNN-based projects:
* [word-rnn](https://github.com/larspars/word-rnn)
* [char-rnn](https://github.com/karpathy/char-rnn)
* [sketch-rnn](https://github.com/hardmaru/sketch-rnn)
* [pixel-rnn](https://github.com/tensorflow/magenta/blob/master/magenta/reviews/pixelrnn.md)
* [neural storyteller](https://github.com/ryankiros/neural-storyteller) (more about this [here](https://medium.com/artists-and-machine-intelligence/a-journey-through-multiple-dimensions-and-transformations-in-space-the-final-frontier-d8435d81ca51#cf7d)
* [lexiconjure - generates definitions for made-up words](https://github.com/rossgoodwin/lexiconjure)
* [torch-rnn server](https://github.com/robinsloan/torch-rnn-server)

