---
layout: post
title:  " Setting up Tensorflow and Jupyter Notebook inside a Google Cloud Compute instance"
date:   2017-06-04 01:52:15 -0700
tags: [google cloud compute, jupyter notebook, tensorflow, gcloud]
categories: [howto]
---

# Setting up Jupyter Notebook inside a Google Cloud Compute instance

## Create cloud compute instance
Try the following settings: 

- zone: US-West-1-b
- machine: 8 vCPU's with 52 GB memory
- boot disk: Ubuntu 14.04 with 200 GB persistent memory

(See overview / more detailed instructions on this [here](https://publicityreform.github.io/findbyimage/create-compute-instance.html))


#### install pip, and python-dev package

`sudo apt-get install python-pip python-dev`

(hit enter / type Y when prompted)

`sudo pip install -U pip`

#### Install tensorflow

Info on installing tensorflow [here](https://www.tensorflow.org/install/)

At this link, look for section Ubuntu > Installing with native pip
python 2.7 CPU only
(or if doing gpu follow that one)

install the latest version of tensorflow by grabbing the link from [here](https://www.tensorflow.org/install/install_linux#TF_PYTHON_URL)
(we're assuming python 2.7, CPU only) 

```sudo pip install --upgrade longurlfromthearticleabove```

##### Now install git and clone the tensorflow repository

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

Try running Jupyter notebook

```
jupyter notebook --no-browser --allow-root
```
