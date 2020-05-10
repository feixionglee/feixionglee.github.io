---
layout: post
title:  "Understanding and Managing Docker Container Volumes"
date:   2019-09-12 23:03:37 +0800
categories: docker
---
[Understanding and Managing Docker Container Volumes. - IONOS](https://www.ionos.com/community/server-cloud-infrastructure/docker/understanding-and-managing-docker-container-volumes/)

In order to understand Docker volumes, it is important to first understand how the Docker file system works.

A Docker image is a collection of read-only layers. When you launch a container from an image, Docker adds a read-write layer to the top of that stack of read-only layers. Docker calls this the **Union File System**.