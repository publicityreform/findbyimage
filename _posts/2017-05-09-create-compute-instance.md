---
layout: post
title:  "create compute instance using google cloud compute"
date:   2017-05-09 01:52:15 -0700
tags: [google cloud compute]
categories: [howto]
---

the goal of this tutorial is to set up a virutal machine on google cloud platform that runs tensorflow and jupyter notebook, then to clone a git repository and play with the code / train models /etc

based on a combination of these two different techniques: [1](https://haroldsoh.com/2016/04/28/set-up-anaconda-ipython-tensorflow-julia-on-a-google-compute-engine-vm/
), [2](https://medium.com/google-cloud/running-jupyter-notebooks-on-gpu-on-google-cloud-d44f57d22dbd). also feel free to make use of google's extensive help docs [here](https://support.google.com/cloud/)

if you would like to be added to the class project ("findbyimage"), email lee or luke to have a user created for you - by joining this project you can see and share virtual machines with the rest of the class, and you don't need to enter any credit card info.

alternatively, the following process should work the same if you would prefer to create your own projects + instances independently - follow the instructions for setting up a new account (you get 300 dollars credit to begin with, but will need to give credit card info). 

login or create account at
[https://cloud.google.com/](https://cloud.google.com/)

if you've already requested access to the class project, it should appear in the menu bar. clicking on this project will show you all of the virtual machine instances that have already been created. 

each "instance" can be thought of as a reservation for processors. you specify the number of CPU's and GPU's you want to use, along with the size of persistent storage. the more processors and storage, the more the instance costs. you pay only when an instance has been started. 

# to create a new instance

to create a custom instance from scratch, select `compute engine > VM instances` from the main menu on the left-hand side. click `create instance`. you will need to specify the location of the instance (try `us-west1-a`) and the number of processors and size of storage (try 1 CPU and 3.75 GB to start with, you can edit to add more later if needed). 

to create an instance using a prest image with some software already installed, select `compute engine > images`. try `ubuntu-1404-trusty-v20170505`. 

once you create an image, it is launched automatically. 

# very important! stop all instances as soon as you are done running them! 

charges can pile up if the instance is left running accidentally - (especially if you've added many processors to the instance!)

# to access / manage the cloud compute instance remotely (from your local computer) you will need to use either ssh or gcloud.

first: generate a ssh key on your local computer:
- for mac OS, launch terminal and type `ssh-keygen -t rsa -f ~/.ssh/google_compute_engine -C username` at the prompt.
- for windows, you should verify this, but i think you can use the PuTTY application and follow [these directions](https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-windows)

...where `google_compute_engine` is the name of the key you will be generating, and `username` is the username you use to login to the cloud service.

second: add this key to an ssh config file on your local computer:
- `echo "IdentityFile ~/.ssh/google_compute_engine" >> ~/.ssh/config` (may be different on windows)

# now you can inter

# install anaconda in your home directory on the cloud instance:

anaconda is a package manager for python that come with many popular python libraries (including jupyter)

get the installer here (using anaconda2 (python 2):
- `wget https://repo.continuum.io/archive/Anaconda2-4.3.1-Linux-x86_64.sh`
update and upgrade and install bzip2 (compute instance doesn't have this already)
- `sudo apt-get update`
- `sudo apt-get upgrade`
- `sudo apt-get install bzip2`
then once the installer has finished copying:
- `bash Anaconda2-4.3.1-Linux-x86_64.sh`

say yes to everything.

once installation is finished, type:

`source ~/.bashrc`

# install git

`sudo apt-get install git`

# install tensorflow

you can use anaconda to install whatever version of tensorflow works with your project. some older repositories may require an earlier version - in the case of sketch-rnn i found this version of tensorflow (0.8) to work ok:

`conda install -c jjhelmus tensorflow=0.8.0rc0`


# to move files back and forth from local machine, you can use scp or gcloud:

to use gcloud in your local terminal [you have to install the sdk](https://cloud.google.com/sdk/downloads)

for example:
`gcloud compute copy-files /localfilepath username@nameofinstance:~/remotefilepath`

# set up ssh tunnel to view jupyter notebooks locally using a browser: 

`$ sudo ssh -i .ssh/google_compute_engine -L 8888:localhost:8888 <username>@<external ip of instance>`


where 8888 is the port specified in jupyter.config

------


to install docker on a cloud computer instance (running ubuntu):
https://store.docker.com/editions/community/docker-ce-server-ubuntu

in google cloud compute, load an instance as an “image” with ubuntu trusty, xenial, or yakkety pre-installed.





