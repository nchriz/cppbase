# cppbase
Repo to create base cpp docker images

# baseImage

This creates a linux environment to compile cpp programs. The distro is ubuntu and it have current packages installed
- make (reinstalled)
- software-properties-common
- g++
- gcc
- git
- wget
- emacs

It have current libraries installed
- Boost


The image have
```
ENTRYPOINT /bin/bash
```
if it's needed to inspect the container.

**ENV BOOST_VERSION** - defines which version of Boost that the image will use.


## run

In the directory run:
```
docker build -t cppbase .
```
This will take a few minutes.

## template dockerFile

The template docker file is to use the above base image to have your work environment to compile the program (here we are using make). The docker file is split into two part:
1. Builder - where all the packages exist to compile an executable file
2. Runner - the image where the executable program will run

The runner is using a distroless base image file. This will make the total size of the image around 20 mb large.

### run

Copy the template file into the directory where you have your Makefile. Run
```
docker build -t NAME -f templateDockerfile .
```
if you haven't renamed the Dockerfile.
