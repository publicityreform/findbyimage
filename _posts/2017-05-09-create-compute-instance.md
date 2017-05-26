---
layout: post
title:  "create compute instance using google cloud compute"
date:   2017-05-09 01:52:15 -0700
tags: [google cloud compute, jupyter, anaconda, gcloud]
categories: [howto]
---

the goal of this tutorial is to set up a virutal machine (a cloud compute instance) on google cloud platform that runs tensorflow and jupyter notebook, then to clone a git repository into this instance so that you can run the included code / train models /etc

the info below is partially based on a combination of these two different techniques: [1](https://haroldsoh.com/2016/04/28/set-up-anaconda-ipython-tensorflow-julia-on-a-google-compute-engine-vm/
), [2](https://medium.com/google-cloud/running-jupyter-notebooks-on-gpu-on-google-cloud-d44f57d22dbd). also feel free to make use of google's extensive help docs [here](https://support.google.com/cloud/)

*note: if you would like to be added to the class project ("findbyimage"), email lee or luke to have a user created for you - by joining this project you can see and share virtual machines with the rest of the class, and you don't need to enter any credit card info.*

alternatively, the following process should work the same if you would prefer to create your own projects + instances independently - follow the instructions for setting up a new account (you get 300 dollars credit to begin with, but will need to give credit card info). 

login or create account at
[https://cloud.google.com/](https://cloud.google.com/)

if you've already requested access to the class project, it should appear in the menu bar. clicking on this project will show you all of the virtual machine instances that have already been created. 

each "instance" can be thought of as a reservation for processors, along with some amount of persistent memory. you specify the number of CPU's and GPU's you want to use, along with the size of persistent storage. the more processors and storage, the more the instance costs. you pay only when an instance has been started (i.e. when you are actively using the processors you've reserved). anything you install or save in your home directory while running an instance will remain there even when you've stopped the instance.

# to create a new instance

in most cases, you can begin by selecting a pre-set image with some software already installed. select `compute engine > images`. try `ubuntu-1404-trusty-v20170505`. 

depending on your task, you may need to make a custom instance from scratch. if you prefer to do this, select `compute engine > VM instances` from the main menu on the left-hand side. click `create instance`, then edit the settings as needed.

whether using a pre-set or a custom image, you will need to specify the location of the instance (try `us-west1-a`) and the number of processors and size of storage (try 1 CPU and 3.75 GB to start with, you can edit to add more later if needed). also select `allow https access`.

once you have created an image, it is launched automatically. 

# very important! stop all instances as soon as you are done running them! 

charges can pile up if the instance is left running accidentally - (especially if you've added many processors to the instance!)

# now you can interact with the compute instance from command line

to access a command line interface for your instance right away, select `open in browser window` from the `SSH` menu.  

alternatively, you can access the instance remotely (from your computer) using ssh or gcloud (skip to [the section on setting up remote access](#to-access-your-cloud-compute-instance-remotely-from-your-computer-you-will-need-to-use-either-ssh-or-gcloud)

once you've connected, type `pwd` to see that you are in a new directory `/home/yourusername`. type `ls` to see that the directory starts off empty. type `cd /home` to see that any other users in the same project also have their own directories. type `cd ~` at any point to return to `/home/yourusername`.

# install anaconda in your home directory on the cloud instance:

anaconda is a package manager for python that come with many popular python libraries (including jupyter)

get the installer here (this uses anaconda2 (for python 2.n) - if your project needs python 3.n, the process is the same for installing anaconda3, just with a different install script. check the [anaconda website](https://www.continuum.io/downloads#linux) for details) :
- `wget https://repo.continuum.io/archive/Anaconda2-4.3.1-Linux-x86_64.sh`

check if `bzip2` is installed already by typing `bzip2 --version` 

if the image you are using doesn't have this program already installed, update, upgrade, and install `bzip2` by typing the following commands one at a time: 
- `sudo apt-get update`
- `sudo apt-get upgrade`
- `sudo apt-get install bzip2`

once you've copied the anaconda installer script and installed bzip2 (if needed), type:
- `bash Anaconda2-4.3.1-Linux-x86_64.sh`

say yes to everything.

once installation is finished, type:

- `source ~/.bashrc`

to enable using anaconda (using the command `conda`)

# install tensorflow

you can use anaconda to install whatever version of tensorflow works with your project. some older repositories may require an earlier version - in the case of sketch-rnn i found this version of tensorflow (0.8) to work ok:

- `conda install -c jjhelmus tensorflow=0.8.0rc0`

to install the most recent version of tensorflow, type

- `conda install tensorflow`

you may get messages about anaconda needing to be updated, say yes to everything.

note that tensorflow is a python library, so to run it, you first need to launch python (by typing `python` at the prompt). now you can run tensorflow commands directly, beginning with:

`import tensorflow as tf`

for instance, to find out which version of tensorflow you are running, type:

`import tensorflow as tf; print(tf.__version__)`

# install git

to clone from github repositories, you will need to install git. from your home directory, type:

- `sudo apt-get install git`

# to access your cloud compute instances remotely from your computer you will need to use either ssh or gcloud

**gcloud** is google's collection of command line tools for managing cloud compute, storage, etc. **ssh** is a general-purpose protocol for remotely-logging in and running programs on a server computer. ssh is more limited in this case, but is still useful for many things such as copying files (using `scp`) or setting up a [tunnel](https://en.wikipedia.org/wiki/Tunneling_protocol) to view jupyter notebooks in a web browser (see [below](#view-jupyter-notebooks-locally-using-a-browser). 

to use gcloud in your local terminal [you have to install the sdk](https://cloud.google.com/sdk/downloads) first, then following [these directions](https://cloud.google.com/compute/docs/gcloud-compute/) to get started, 
- type `gcloud init` in your local terminal - this will create a default configuration for gcloud to use. 
- a browser window should open asking you to login - make sure to login with the same account that you created the cloud compute instance with. 
- you will then be asked to grant authorization to gcloud, say yes to everything. 
- you will be asked to specify a zone for the default configuration, make sure to select the same zone that you used in the cloud compute instance (e.g. `us-west-1-a`)
- to connect, type `gcloud compute ssh yourusername@yourinstance` in your local terminal
- if an ssh key pair for google_cloud_compute does not already exist, this will be automatically created and configured by gcloud when you first connect. 

*alternatively*, you can use `ssh` from your computer:

interacting with your instance by using `gcloud` will automatically generate an ssh key pair to allow secure access from your local computer, and you can skip to the bottom of this section. if you're only using `ssh` and not `gcloud`, you will need to manually generate a ssh key pair on your local computer, then add it to the cloud compute instance:
- for mac OS, launch terminal and type `ssh-keygen -t rsa -f ~/.ssh/google_compute_engine -C username` at the prompt.
   - where `google_compute_engine` is the name of the key you will be generating, and `username` is the username you use to login to the cloud service (i.e. everything before the `@` in your email address).
   - you will be asked for a password, make one if you like.
   - this makes two files inside a hidden folder named ssh in your home directory: a private key (`google_compute_engine`) and a public key (`google_compute_engine.pub`)
- for windows, you should verify this, but i think you can use the PuTTY application and follow [these directions](https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-windows)

add the private key to an ssh config file on your local computer:
- `echo "IdentityFile ~/.ssh/google_compute_engine" >> ~/.ssh/config` in your local terminal

copy the public key to the compute instance:
- type `cat google_compute_engine.pub` in your local terminal, then copy all of the output (from `ssh-rsa` to your username)
- back in the google cloud platform dashboard, in the top left menu, select `compute engine > metadata` then select `ssh keys`. click edit to paste in the key you just copied, then save. 

now find the external IP address of your instance by navigating back to the main `VM instances` page. note that this address changes each time you start and stop the instance. 

now you should be able to connect to the cloud instance by typing `ssh yourusername@yourexternalip` in your local terminal.

# to move files (or folders) back and forth from a local machine, you can use either scp (part of the ssh protocol) or gcloud compute:

from your local computer:

using `scp`:

- first type `exit` to leave `ssh` if it's running, or launch a new terminal window.
- type `scp ~/localfilepath yourusername@yourexternalip:~/remotefilepath`

or using `gcloud`:

- `gcloud compute copy-files ~/localfilepath username@nameofinstance:~/remotefilepath`

where `~/` is your home directory, `localfilepath` is the rest of the path to the file or folder you want to upload, `username` is the username you log in to google cloud compute with, and `name of instance` is... well, you get it. 


# view jupyter notebooks locally using a browser 

`jupyter` is included with anaconda. launch it from the remote command line (either in the browser, or while ssh'd in) by typing `jupyter notebook --no-browser` at the prompt. 

next, create a tunnel to map the cloud compute instance's port 8888 to your local port 8888. from command line on your local computer, type: 
- `ssh -i .ssh/google_compute_engine -L 8888:localhost:8888 yourusername@your-instance-external-ip` 

if you are using **gcloud** to connect instead of **ssh** the command to set up a tunnel is slightly different:

- `gcloud compute ssh name-of-your-instance -- -N -p 22 -D localhost:8888`

*if you've already generated an ssh key pair (manually, or by launching `gcloud`) then you should be able to connect - if you get a `permission denied` error, you may need to confirm that these keys have been properly set up ([see above](#-to-access-your-cloud-compute-instances-remotely-from-your-computer-you-will-need-to-use-either-ssh-or-gcloud)*

(note: 8888 is the default port used by jupyter. you can change it in `~/.jupyter/jupyter_notebook_config.py` if needed.)

finally, open a browser window and go to `http://localhost:8888`. you should see the jupyter dashboard, showing any folders and files that you've saved to your cloud compute instance's home directory. from this browser window, you can now create, upload or launch any .ipynb (jupyter notebook) files. 

if you get an error that you need a token, read the remote terminal output, you should see something like: `http://localhost:8888/?token=xxxxxxxxxxxxx` where `xxxxxxxxxxxxx` is the token - copy and paste that to launch the jupyter dashboard. 

# build a project

while connected to your compute instance via `ssh`, use `git` to clone a repository from github into your home directory, or make your own python files (in a text editor, to be uploaded and run from the command line, or inside a new jupyter notebook). 

# update or install any dependencies 

you can always use `conda` or `pip` to install or update any dependencies your project requires.

# very important! stop all instances as soon as you are done running them! 
