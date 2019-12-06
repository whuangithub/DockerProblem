This project contains the problems I met during installing and using Docker.

Install I installed Docker Engine - Community to Ubuntu 18.04 following the instruction from the official website of docker

```
when processing
    sudo apt-get update
I met a problem similar to
    The repository 'http://ppa.launchpad.net/armagetronad-dev/ppa/ubuntu bionic Release' does not have a Release file.
    N: Updating from such a repository can't be done securely, and is therefore disabled by default.
    N: See apt-secure(8) manpage for repository creation and user configuration details.
And the repository needs to be removed
    sudo apt-add-repository -r ppa:armagetronad-dev/ppa
    sudo apt update -q


when processing
    sudo apt-get install docker-ce docker-ce-cli containerd.io
I met a problem related to the version of package "libseccomp2" and I manually downloaded it from the debian website.
```

Use Just following the instruction from tensorflow website docker pull tensorflow/tensorflow:latest-gpu-py3 And then I installed jupyter by myself And to make sure I don't have to install the packages every time I use docker, I need to commit and sace teh new container docker commit

<container id="">
  <new name="" of="" the="" new="" image="">
    for container ID use
        docker ps -a</new>
</container>

```
Open jupyter notebook with docker
    docker run --gpus all -it -p 8888:8888 -v /HDD1:/HDD1 mytensorflow
-p 8888:8888 is to allocate port to jupyter notebook
-v <path on host>:<path on container> is to share files between host and docker
then to start jupyter notebook use
    jupyter notebook --port 8888 --ip=0.0.0.0 --allow-root

One may would like to use command line during using jupyter notebook, to open a new terminal window that connect to the same container:
    docker exec -it <container> bash

Manage docker as a non-root user
    sudo groupadd docker
    sudo usermod -aG docker $USER
```



Installing OpenCV
	apt-get update
	apt-get install python3-opencv
