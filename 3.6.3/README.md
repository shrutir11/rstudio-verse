[![Project Supported by CyVerse](https://de.cyverse.org/Powered-By-CyVerse-blue.svg)](https://learning.cyverse.org/projects/vice/en/latest/) [![Project Status: WIP – Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3246938.svg)](https://doi.org/10.5281/zenodo.3246938) [![license](https://img.shields.io/badge/license-GPLv2-blue.svg?style=flat-square)](https://opensource.org/licenses/GPL-2.0) ![GitHub all releases](https://img.shields.io/github/downloads/cyverse-vice/rstudio-verse/total?style=flat-square)

# rstudio-verse

Based on the [Rocker-Project.org](https://rocker-project.org) Docker [RStudio `verse` container](https://hub.docker.com/r/rocker/verse) for CyVerse Discovery Environment (DE) data science workbench. CyVerse DE requires additional configuration files (e.g. `nginx`) to be compatible with our Condor and Kubernetes orchestration. 

[An Introduction to Rocker: Docker Containers for R](https://journal.r-project.org/archive/2017/RJ-2017-065/RJ-2017-065.pdf) Carl Boettiger and Dirk Eddelbuettel, The R Journal (2017) 9:2, pages 527-536. [https://doi.org/10.32614/RJ-2017-065 ](https://doi.org/10.32614/RJ-2017-065)

[![CircleCI](https://circleci.com/gh/cyverse-vice/rstudio-verse.svg?style=svg)](https://circleci.com/gh/cyverse-vice/rstudio-verse) ![GH actions branch parameter](https://github.com/github/docs/actions/workflows/main.yml/badge.svg?branch=main) ![GitHub commits since tagged version](https://img.shields.io/github/commits-since/cyverse-vice/rstudio-verse/latest/main?style=flat-square) [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse) 

quick launch | size | 
------------ | ---- | 
<a href="https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=b548d3e2-3310-45ae-8b1f-78e8cce2cfaf&app-id=3548f43a-bed1-11e9-af16-008cfa5ae621" target="_blank"><img src="https://img.shields.io/badge/Verse-latest-blue?style=plastic&logo=rstudio"></a> | [![SIZE](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/latest.svg)](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/latest)
<a href="https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=b548d3e2-3310-45ae-8b1f-78e8cce2cfaf&app-id=3548f43a-bed1-11e9-af16-008cfa5ae621" target="_blank"><img src="https://img.shields.io/badge/Verse-4.0.5-blue?style=plastic&logo=rstudio"></a> | [![SIZE](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/4.0.5.svg)](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/4.0.5)
<a href="https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=97782f8c-8c6f-4969-8c4e-2dd9d5bf5f96&app-id=a8b21a2c-e6f4-11ea-844a-008cfa5ae621" target="_blank"><img src="https://img.shields.io/badge/Verse-4.0.0ubuntu18.04-blue?style=plastic&logo=rstudio"></a> | [![SIZE](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/4.0.0-ubuntu18.04.svg)](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/4.0.0-ubuntu18.04) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/rstudio-verse?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/rstudio-verse)
<a href="https://de.cyverse.org/de/?type=quick-launch&quick-launch-id=97782f8c-8c6f-4969-8c4e-2dd9d5bf5f96&app-id=a8b21a2c-e6f4-11ea-844a-008cfa5ae621" target="_blank"><img src="https://img.shields.io/badge/Verse-3.6.3-blue?style=plastic&logo=rstudio"></a> | [![SIZE](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/3.6.3.svg)](https://img.shields.io/docker/image-size/cyversevice/rstudio-verse/3.6.3) 



# Instructions

## Run this Docker locally or on a Virtual Machine

To run these containers, you must first pull them from DockerHub

```
docker pull cyversevice/rstudio-verse:latest
```

```
docker run -it --rm -v /$HOME:/app --workdir /app -p 8787:80 -e REDIRECT_URL=http://localhost:8787 cyversevice/rstudio-verse:latest
```

The default username is `rstudio` and password is `rstudio1`. To reset the password, add the flag `-e PASSWORD=<yourpassword>` in the `docker run` statement.

## Build your own Docker container and deploy on CyVerse VICE

This container is intended to run on the CyVerse data science workbench, called [VICE](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/index.html). 

Unless you plan on making changes to this container, you should just use the existing launch button above. 

###### Developer notes

To build your own container with a Dockerfile and additional dependencies, pull the pre-built image from DockerHub:

```
FROM cyversevice/rstudio-verse:latest
```

Follow the instructions in the [VICE manual for integrating your own tools and apps](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/developer_guide/building.html).
