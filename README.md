# cppbase
Repo to create base cpp docker images

## baseImage

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


###

```
ENV BOOST_VERSION - defines which version of Boost that the image will use.
```

The image have
```
ENTRYPOINT /bin/bash
```
if it's needed to inspect the container.

### run

In the directory run:
```
docker build -t cppbase .
```
This will take a few minutes.
