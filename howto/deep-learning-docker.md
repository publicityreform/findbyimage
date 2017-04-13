
download and install the “docker” applicatin from https://docs.docker.com/engine/installation/

in terminal, type `docker run hello-world` to see if docker has installed correctly

use docker to get [this deep learning container docker](https://github.com/floydhub/dl-docker) by typing `docker pull floydhub/dl-docker:cpu`

`mkdir sharedfolder`

`docker run -it -p 8888:8888 -p 6006:6006 -v [yourhomedirectoryhere]/sharedfolder:/root/sharedfolder floydhub/dl-docker:cpu bash`

on my computer [yourhomedirectoryhere] would be replaced with /Users/luke

https://github.com/soumith/dcgan.torch

`cd sharedfolder`

`git clone https://github.com/soumith/dcgan.torch.git`

`luarocks install optnet`

`gpu=0 batchSize=1 display=0  name=g04 net=~/sharedfolder/celebA_25_net_G.t7 th generate.lua`
