---
layout: post
title:  "How to Install and Access Jupyter Notebook via Docker"
date:   2017-04-11 21:52:15 -0700
tags: [Jupyter, Docker, Terminal]
categories: [How To]
---

# How to install/access Jupyter Notebook via the Floydhub docker and access a notebook

Note: We previously downloaded and installed [Docker](https://www.docker.com) and then we made a directory named ```sharedfolder``` in our home directory.

1. Turn on docker (you may have this installed and run it via your Mac Menu bar). 
2. In Terminal, run ```docker run -it -p 8888:8888 -p 6666:6666 -v /Users/<yourAccountName>/sharedfolder/:/root/sharedfolder floydhub/dl-docker:cpu bash```. If you don't have it all installed, it will install (wait...). Make sure you replace ```<YourAccountName>```.
3. It may prompt you for your password. Type it in.
4. Run ```jupyter notebook```
5. Go to browser. Type in ```localhost:8888```
6. In the browser ipython/jupyter, click New > Open Terminal (this all happens in the browser)
7. In Jupyter in the browser Terminal, go to your sharedfolder ```cd sharedfolder```
8. In a separate window, go to our findbyimage repository, go to ```notebooks/word2vec/``` or click [here](https://github.com/publicityreform/findbyimage/tree/master/notebooks/word2vec).
9. Click on ```word2vec.ipynb.zip``` and click on the download button and download it into the sharedfolder on your computer.
10. Unzip it.
11. Go back to your jupyter notebook in the browser and click on the word2vec.ipynb notebook to launch it
