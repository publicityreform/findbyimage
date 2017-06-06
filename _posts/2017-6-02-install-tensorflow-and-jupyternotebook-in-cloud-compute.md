---
layout: post
title:  " Setting up Tensorflow and Jupyter Notebook inside a Google Cloud Compute instance"
date:   2017-06-04 01:52:15 -0700
tags: [google cloud compute, jupyter notebook, tensorflow, gcloud]
categories: [howto]
---

# Setting up Jupyter Notebook inside a Google Cloud Compute instance

## Create cloud compute instance
Info [here](https://publicityreform.github.io/findbyimage/create-compute-instance.html)  

#### install pip (upgraded one) and numpy

```
sudo apt-get install python-dev #this will install numpy
sudo apt-get install python-pip
sudo pip install -U pip
```

Run ```pip list``` to see what you already have

#### Install tensorflow

Info on installing tensorflow [here](https://www.tensorflow.org/install/)

At this link, look for section Ubuntu > Installing with native pip
python 2.7 CPU only
(or if doing gpu follow that one)

```sudo pip install --upgrade longurlfromthearticleabove```

##### Now install git and tensorflow

```
sudo apt-get install git
```

Now clone tensorflow github repository

```
git clone https://github.com/tensorflow/tensorflow.git
```

##### Install jupyter notebook

```
sudo pip install jupyter
```

Reload bashrc

```
source ~/.bashrc
```

Try running Jupyter notebook

```
jupyter notebook --no-browser
```
