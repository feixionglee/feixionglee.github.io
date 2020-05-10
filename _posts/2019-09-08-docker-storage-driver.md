---
layout: post
title:  "Docker storage driver"
date:   2019-09-08 20:04:05 +0800
categories: docker
---
[About storage drivers \| Docker Documentation](https://docs.docker.com/v17.12/storage/storagedriver/#container-and-layers)

The major difference between a container and an image is the top writable layer. All writes to the container that add new or modify existing data are stored in this writable layer. When the container is deleted, the writable layer is also deleted. The underlying image remains unchanged.