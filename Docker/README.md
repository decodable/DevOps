# Overview
![Docker Overview](http://interactive.blockdiag.com/image?compression=deflate&encoding=base64&src=eJx9kMFOhDAURffzFS_j2qDGuKmaDCDGxJVbY8iDdqCZymvaMmrM_LulTEcIxq4o5_T29VaK6h2X2AD3H8LA9wr84mKLvXKlbVELuANDfccFr-iTzXjjgS5rUmS8tT4rwlqPktXYlR-Su9azy6sLBpAk8SjsUfUCpIWb61XQN_CqsBJqCMrDMFupxPptDEsXFJ7esTnxbMkz6hzKTpjo5BPnUTp4EZqsdGS-ovEwMZ6pRgW5tLtIi-Ud84hghU6OPYZ3MUgZZOz0g4wUfjInqfNJmowzKN3ID39G5AyKyI8vuT2_nzWme9smulfqd9hBSf9TNjAYsd9Bz6abaRmKkCcW96Hvww9Mm5zY)

1. docker build - build an image from a Docker file. 
2. docker save - save an image to a local file - tarball.
3. docker load - load an image from a local file.
4. docker pull - load in image from a repository - docker hub
5. docker push - save an image to a repository.
6. docker commit - commit the change in a container to an image.

It is better to use Dockerfiles to manage images in a documented and maintainable way.

However, docker images will save you time of buillding and make sure all can get the same container.

# Images
```
docker pull ubuntu:16.04
docker images
docker rmi
docker history
docker build -t name .
```
My Images:
1. [ubuntu_cpp_dev](https://hub.docker.com/r/codible/ubuntu_cpp_dev/) - Develop env for C/C++ based on ubuntu 18.04. Integrate GCC, CMake, Google Test, Cppcheck and Valgrind.
2. [clang_dev](https://hub.docker.com/r/codible/clang_dev/) - Develop env for clang.
3. [ml_dev](https://hub.docker.com/r/codible/ml_dev/) - Develop env for machine learning. Only Octave was installed.


# Containers
Container is an instance of image.
```
docker ps -a
docker inspect
docker run --rm -it -v /data:/data:rw --cap-add=SYS_PTRACE -p 3002:3002 3107e358f41c /bin/bash
docker create
docker start
docker exec -ti 3107e358f41c /bin/bash
docker stop
docker kill
docker rm
docker pause
docker unpause
docker logs
docker stats
docker top
docker diff
```

# Start GUI program in Container from virtual machine
```
export DISPALY=:0.0
ssh -X localhost
docker run --rm -it --env="DISPLAY" -v /data/:/data/:rw --volume="$HOME/.Xauthority:/root/.Xauthority:rw" --net=host codible/ml_dev /bin/bash
```

# References
0. [Manage Docker as a non-root user](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)
1. [Understanding Docker "Container Host" vs. "Container OS" for Linux and Windows Containers](http://www.floydhilton.com/docker/2017/03/31/Docker-ContainerHost-vs-ContainerOS-Linux-Windows.html)
2. [Docker Base Image OS Size Comparison](https://www.brianchristner.io/docker-image-base-os-size-comparison/)
3. [Push a Docker Image to a Personal Repository](http://karlcode.owtelse.com/blog/2017/01/25/push-a-docker-image-to-personal-repository/)
4. [Named Volumes in Dockerfile](https://github.com/moby/moby/issues/30647)
5. [Docker development best practices](https://docs.docker.com/develop/dev-best-practices/)
6. [Using Docker and Docker Compose for Local Development and Small Deployments](https://www.codementor.io/jquacinella/docker-and-docker-compose-for-local-development-and-small-deployments-ph4p434gb)
7. [An Introduction to Docker for Embedded Developers](https://blog.feabhas.com/2017/09/introduction-docker-embedded-developers-part-1-getting-started/)
8. Architecting Containers [Part1](https://rhelblog.redhat.com/2015/07/29/architecting-containers-part-1-user-space-vs-kernel-space/) [Part2](https://rhelblog.redhat.com/2015/09/17/architecting-containers-part-2-why-the-user-space-matters-2/) [Part3](https://rhelblog.redhat.com/2015/11/10/architecting-containers-part-3-how-the-user-space-affects-your-application/)
9. [Docker Container’s Filesystem Demystified](https://medium.com/@nagarwal/docker-containers-filesystem-demystified-b6ed8112a04a)
10. [Docker RUN vs CMD vs ENTRYPOINT](http://goinbigdata.com/docker-run-vs-cmd-vs-entrypoint/)
11. [COMPLETE INTRO TO CONTAINERS](https://btholt.github.io/complete-intro-to-containers/)
