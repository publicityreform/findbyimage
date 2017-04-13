
download and install the “docker” applicatin from https://docs.docker.com/engine/installation/

in terminal, type `docker run hello-world` to see if docker has installed correctly

use docker to get [this deep learning container docker](https://github.com/floydhub/dl-docker) by typing `pull floydhub/dl-docker:cpu`

`mkdir sharedfolder`

`docker run -it -p 8888:8888 -p 6006:6006 -v [yourhomedirectoryhere]/sharedfolder:/root/sharedfolder floydhub/dl-docker:cpu bash`

on my computer [yourhomedirectoryhere] would be replaced with /Users/luke
