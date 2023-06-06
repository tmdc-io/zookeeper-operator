# Steps to Docker build and push to DockerHub private repo

Once you are ready with your changes - 

Run **git tag** command from root directory

First, please check the previous tag and use the incremental version of that.
Create git tag in local

```shell
git tag 0.2.16-d1
```
Push the tag to the remote repo

```shell
git push origin 0.2.16-d1
```
It will trigger the **TMDC Docker Image CI workflow** github action pipeline.
**zookeeper-operator** and **zookeeper** docker image will be built with the **TAG** and pushed to DOCKER HUB private repo **rubiklabs**

**NOTE:** Always maintain the semantic version (major.minor.patch) fixed and provide a suffix **-d** with it.
Tag will be incremental like ```shell major.minor.patch-d(+1 increment)```

ex ```shell 0.2.16-d1, 0.2.16-d2, 0.2.16-d3 ... ``` like that

We can update and push the **major.minor.patch** section of the tag once there is a release of docker image with official repo with same major/minor/patch version and also if we merge the changes to our repo.

ex: Lets say 0.2.17 or 0.3.1 image version released . Once changes have been merged to our repo we will use tag 0.2.17-d(+1) or 0.3.1-d(+1).
