[![Project Supported by CyVerse](https://img.shields.io/badge/Supported%20by-CyVerse-blue.svg)](https://learning.cyverse.org/projects/vice/en/latest/) [![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4543625.svg)](https://doi.org/10.5281/zenodo.4543625) [![license](https://img.shields.io/badge/license-BSD3-red.svg?style=flat-square)](https://opensource.org/licenses/BSD-3-Clause) ![GitHub all releases](https://img.shields.io/github/downloads/cyverse-vice/jupyterlab-tensorflow/total?style=flat-square)

# jupyterlab-tensorflow
[Project Jupyter](https://jupyter.org/) Tensorflow Notebook with CyVerse addins.

Jupyter Lab Datascience image built from the [Tensorflow Notebook](https://hub.docker.com/r/jupyter/tensorflow-notebook) for [CyVerse VICE](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/index.html). Project Jupyter's base image requires a couple additional configuration files for it be compatible with CyVerse Kubernetes orchestration and iRODS data store.

[![CircleCI](https://circleci.com/gh/cyverse-vice/jupyterlab-tensorflow.svg?style=svg)](https://circleci.com/gh/cyverse-vice/jupyterlab-tensorflow) [![DockerHub](https://img.shields.io/badge/DockerHub-gray.svg?style=popout&logo=Docker)](https://hub.docker.com/r/cyversevice/jupyterlab-tensorflow) ![GitHub commits since tagged version](https://img.shields.io/github/commits-since/cyverse-vice/jupyterlab-tensorflow/latest/main?style=flat-square) ![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/cyversevice/jupyterlab-tensorflow)

quick launch | tag | size |  
------------ | --- | ---- |
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | ![Docker Image Version (tag latest semver)](https://img.shields.io/docker/v/cyversevice/jupyterlab-tensorflow/latest?style=flat-square) | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/cyversevice/jupyterlab-tensorflow/latest?style=flat-square) 
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | ![Docker Image Version (tag 2.2.9 semver)](https://img.shields.io/docker/v/cyversevice/jupyterlab-tensorflow/2.2.9?style=flat-square) | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/cyversevice/jupyterlab-tensorflow/2.2.9?style=flat-square) 
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | ![Docker Image Version (tag geospatial-2.2.9 semver)](https://img.shields.io/docker/v/cyversevice/jupyterlab-tensorflow/geospatial-2.2.9?style=flat-square) | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/cyversevice/jupyterlab-tensorflow/geospatial-2.2.9?style=flat-square) 

# Instructions

## Run Docker locally or on a Virtual Machine

To run the JupyterLab, you must first `pull` from DockerHub, or activate a [CyVerse Account](https://user.cyverse.org/services/mine) and launch in the Discovery Environment VICE.

The container for running JupyterLab is hosted on DockerHub and can be started locally:

```
docker pull cyversevice/jupyterlab-tensorflow:latest
```

```
docker run -it --rm -d cyversevice/jupyterlab-tensorflow:latest
```

## Run Docker with NVIDIA GPU

```
docker run --gpus all -it --rm -d cyversevice/jupyterlab-tensorflow:latest
```

## Run Docker container in CyVerse VICE

Unless you plan on making changes to this container, you should just use the existing launch button above.

You can build a new Docker container with additional dependencies from this Docker Hub image by using the `FROM cyversevice/jupyterlab-tensorflow:latest` at the beginning of your own Dockerfile.

###### Developer notes

To test the container locally:

```
docker run --gpus all -it --rm -v /$HOME:/work --workdir /work -p 8888:8888 -e REDIRECT_URL=http://localhost:8888 cyversevice/jupyterlab-tensorflow:latest
```
