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
docker push dasisdormax/cpp-ubuntu:noble-1    # do not use -a
docker push dasisdormax/cpp-ubuntu:latest     # do not use -a
~~~

## Local Testing with Gitlab Runners

Setup local runner:

~~~.sh
docker pull gitlab/gitlab-runner

# Create test repository and a local runner in Gitlab Web UI.
# Make sure to use the correct tags and disable instance runners.
#
# Paste gitlab-runner register command
# Use docker executor and default image (ruby:3.3)
~~~

Configure to use local images by editing ~/.gitlab-runner/config.toml ...

~~~
[[runners]]
  [runners.docker]
    pull_policy = "if-not-present"
    allowed_pull_policies = ["always", "if-not-present"]
~~~

Start your local runner with `gitlab-runner run` and start your pipeline.
~~~

