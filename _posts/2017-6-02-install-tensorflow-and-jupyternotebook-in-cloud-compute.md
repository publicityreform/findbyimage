---
layout: post
title:  " Setting up Tensorflow and Jupyter Notebook inside a Google Cloud Compute instance"
date:   2017-06-04 01:52:15 -0700
tags: [google cloud compute, jupyter notebook, tensorflow, gcloud]
categories: [howto]
---

# Setting up Jupyter Notebook inside a Google Cloud Compute instance

1. Create cloud compute instance
Info [here](https://publicityreform.github.io/findbyimage/create-compute-instance.html)  

2. install pip (upgraded one) and numpy

```
sudo apt-get install python-dev (this will install numpy)
sudo apt-get install python-pip
sudo pip install -U pip
```

3. run ```pip list``` to see what you already have

4. Install tensorflow

Info on installing tensorflow [here](https://www.tensorflow.org/install/)

At this link, look for section Ubuntu > Installing with native pip
python 2.7 CPU only
(or if doing gpu follow that one)

```sudo pip install --upgrade longurlfromthearticleabove```

5. Now install git

```
sudo apt-get install git
```

6. Now clone tensorflow github repository

```
git clone https://github.com/tensorflow/tensorflow.git
```

7. Install jupyter notebook

```
sudo pip install jupyter
```

8. Reload bashrc

```
source ~/.bashrc
```

9. Install jupyter notebook

```
sudo pip install jupyter
```

10. Try running Jupyter notebook

```
juypter notebook --no-browser
```
