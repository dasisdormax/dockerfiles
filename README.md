# Dockerfiles

## Prerequisites

Install `docker-buildx` (e.g. using APT).

Add yourself to the `docker` group (or build using sudo)

## Build Instructions


Run this to build.

~~~.sh
cd cpp-ubuntu
docker build -f Dockerfile.noble-1 -t dasisdormax/cpp-ubuntu:noble-1 .
docker images --digests
docker image tag 4e436fca6e0e dasisdormax/cpp-ubuntu:latest
docker push -a dasisdormax/cpp-ubuntu
~~~

## Testing

~~~.sh
docker pull gitlab/gitlab-runner
# Paste gitlab-runner register command
# Use docker executor and default image (ruby:3.3)
gitlab-runner run
~~~

Alternative setup (untested)

~~~.sh
docker pull gitlab/gitlab-runner
docker volume create gitlab-runner-config
docker run -d --name gitlab-runner --restart always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v gitlab-runner-config:/etc/gitlab-runner \
  gitlab/gitlab-runner:latest
~~~
