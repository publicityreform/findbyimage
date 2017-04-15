these instructions are for using a docker container to run deep-learning libraries such as torch, tensorflow, caffe, theano, keras, etc. on your own computer, using [terminal](IntroToCommandLine.md) and [git](HowToUseGitHub.md). the reason for using one docker container with all of these libraries is that it simplifies the process of keeping track of conflicting dependencies - for instance if you want to compare a torch implementation of a process with a tensorflow implementation, or if some example code is given in caffe and you don't want to take the time to set up a new install just to try it. if you'd prefer, it's possible to install separate docker containers to run just one of any of these libraries on their own, or to install any of these from scratch (without docker) if you would prefer more customization options, but that's beyond the scope of this document. 

note: these instructions are specific to macOS - there may be some differences in the commands if you are using linux or windows *(please add notes below if you find differences or better methods!)*

------

download and install the “docker” application from https://docs.docker.com/engine/installation/

[docker](https://github.com/docker/docker) is an open-source project that consists of "containers" that include all necessary dependencies and environmental variables. when you run a docker container, it runs as a virtual machine that is isolated from other installed software on your computer, even other docker containers. Note that any changes you make within the docker container only persist while docker is running, and everything is re-set when the container is run again.

in terminal, type `docker run hello-world` to verify that docker has installed correctly.

use docker to download [this deep learning docker container](https://github.com/floydhub/dl-docker) by typing

`docker pull floydhub/dl-docker:cpu`

you can read more about what this specific docker container does [here](https://github.com/floydhub/dl-docker). basically, it runs a virtual version of ubuntu linux that has [Tensorflow](https://www.tensorflow.org/), [Caffe](http://caffe.berkeleyvision.org/), [Theano](http://deeplearning.net/software/theano/), [Keras](http://keras.io/), [Lasagne](http://lasagne.readthedocs.io/en/latest/), [Torch](http://torch.ch/), [iPython/Jupyter Notebook](http://jupyter.org/), [Numpy](http://www.numpy.org/), [SciPy](https://www.scipy.org/), [Pandas](http://pandas.pydata.org/), [Scikit Learn](http://scikit-learn.org/), [Matplotlib](http://matplotlib.org/), and [OpenCV](http://opencv.org/) all installed and working without conflict. very helpful!

once this download is complete, create a folder named `sharedfolder`. we'll make this folder accessible from within the docker container in the next step.

`mkdir sharedfolder`

`docker run -it -p 8888:8888 -p 6006:6006 -v [yourhomedirectoryhere]/sharedfolder:/root/sharedfolder floydhub/dl-docker:cpu bash`

on my computer `[yourhomedirectoryhere]` would be replaced with `/Users/luke`. type `pwd` in terminal to see which directory you are currently in. type `ls` to see the contents of your current directory - make sure the folder `sharedfolder` that you just created is in fact inside this directory.

`-p 8888:8888 -p 6006:6006` open these ports to the docker container (to view a [jupyter notebook](http://jupyter.org/), or a [tensorboard graph](https://www.tensorflow.org/get_started/graph_viz), for example). if you receive an error that these ports are currently in use, try another port number, or omit this part of the command for now.

`bash` is included at the end of the command to specify that you'd like to access docker via `bash`. you can specify another shell if you like. 

once the docker container is running, you can launch jupyter notebooks (type `jupyter notebook`), caffe (type `caffe`), or torch (type `th`). to use included python libraries, launch python (type `python`) and then import the library you want to use. for example: use tensorflow by typing `import tensorflow as tf`. from here you can [get started](https://www.tensorflow.org/get_started/get_started) as if you'd installed tensorflow by any other means.  

to exit docker, type `control+d`. make sure anything that you want to save (datasets, code, trained models, outputs, etc) is inside `/sharedfolder`, as everything else inside the docker container will reset the next time you run it. 

------

as an example, we'll try this deep convolutional generative adversarial network project written in torch: https://github.com/soumith/dcgan.torch

run the docker container.

enter the `sharedfolder` you created earlier by typing `cd sharedfolder`.

use git to clone the project repository into your `sharedfolder` so that it can be accessed from within docker:

`git clone https://github.com/soumith/dcgan.torch.git`

enter the directory you've just created for the project by typing `cd dcgan.torch`.

torch is written in [lua](https://en.wikipedia.org/wiki/Lua_(programming_language)), which is a beautiful language with an interesting history. use lua's package manager `luarocks` to install the necessary `optnet` package:

`luarocks install optnet`

at this point you can try out the dcgan.torch project code to train an image generator on existing datasets, or your own set of images, or use pre-trained models to generate images right away. look at the [project readme](https://github.com/soumith/dcgan.torch) for a walkthrough of the various options, or download a pre-trained model here, saving it inside your `sharedfolder` directory:
  - [celebrity faces](https://github.com/soumith/lfs/raw/master/dcgan.torch/celebA_25_net_G.t7) (uses the [celebA dataset](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html_))
  - [bedrooms](https://github.com/soumith/lfs/raw/master/dcgan.torch/bedrooms_4_net_G.t7) (uses the [LSUN dataset](http://lsun.cs.princeton.edu/))
  
type the following command to use a pre-trained model (from inside the `dcgan.torch` directory) to generate an image named g01.png inside your `dcgan.torch` directory:

`gpu=0 batchSize=1 display=0  name=g01 net=~/sharedfolder/celebA_25_net_G.t7 th generate.lua`

change `~/sharedfolder/celebA_25_net_G.t7` to point to whichever model you want to use (celebrity faces, in this case).

change `batchsize` to generate more than one image at a time. 

change `g01` to another filename to create a new image. 

you can play with other options like `imsize` and `noisemode` - see the [project readme](https://github.com/soumith/dcgan.torch) for all options. 

if you are interested in getting deeper with generative adversarial networks (GAN's), here are a some suggested readings:

  - https://blog.openai.com/generative-models/
  - https://arxiv.org/pdf/1406.2661.pdf





