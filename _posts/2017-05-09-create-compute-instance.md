---
layout: post
title:  "create compute instance using google cloud compute"
date:   2017-05-09 01:52:15 -0700
tags: [google cloud compute]
categories: [howto]
---

login or create account at
https://cloud.google.com/

the goal is to set up a virutal machine that runs tensorflow and jupyter notebook, then to clone a git repository and play with the code / train models /etc

based on a combination of these two [different](https://haroldsoh.com/2016/04/28/set-up-anaconda-ipython-tensorflow-julia-on-a-google-compute-engine-vm/
) [techniques](https://medium.com/google-cloud/running-jupyter-notebooks-on-gpu-on-google-cloud-d44f57d22dbd)


# to access the cloud compute instance remotely (from your local computer) you will need to use either ssh or gcloud.

first: generate a ssh key on your local computer:
- `ssh-keygen -t rsa -f ~/.ssh/google_compute_engine -C username`

where google_compute_engine is the name of the key you will be generating (can be anything), and username is the username you use to login to the cloud service.

second: add this key to an ssh config file on your local computer:
- `echo "IdentityFile ~/.ssh/google_compute_engine" >> ~/.ssh/config`

# to move files back and forth from local machine, you can use scp or gcloud:

for example:
`gcloud compute copy-files nameofinstance:~/remotefilepath /localfilepath`

# set up ssh tunnel to view jupyter notebooks locally using a browser: 

`$ sudo ssh -i .ssh/google_compute_engine -L 8888:localhost:8888 <username>@<external ip of instance>`


where 8888 is the port specified in jupyter.config

------


---------

to install docker on a cloud computer instance (running ubuntu):
https://store.docker.com/editions/community/docker-ce-server-ubuntu

in google cloud compute, load an instance as an “image” with ubuntu trusty, xenial, or yakkety pre-installed.

—————



`sudo gcloud components update && gcloud components install beta`

`gcloud beta compute regions describe us-east1`

If the limit is <1.0, then please request an increase in the limit at https://console.cloud.google.com/compute/quotas . In my experience, Google has approved the request instantly.

`~$ gcloud beta compute instances create gpu-deep-learner --machine-type n1-standard-2 --zone us-east1-d --accelerator type=nvidia-tesla-k80,count=1 --image-family ubuntu-1604-lts --image-project ubuntu-os-cloud --boot-disk-size 50GB --maintenance-policy TERMINATE --restart-on-failure`



~$ curl -O http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.61-1_amd64.deb

~$ sudo dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
~$ sudo apt-get update
~$ rm cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
~$ sudo apt-get install cuda -y

~$ nvidia-smi

~$ echo 'export CUDA_HOME=/usr/local/cuda' >> ~/.bashrc
~$ echo 'export PATH=$PATH:$CUDA_HOME/bin' >> ~/.bashrc
~$ echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CUDA_HOME/lib64' >> ~/.bashrc
~$ source ~/.bashrc



