# syntax=docker/dockerfile:1
FROM dasisdormax/cpp-ubuntu:jammy-1
MAINTAINER Maximilian Wende <maximilian.wende@freiberginstruments.com>
LABEL Description="Ubuntu-based C++ build environment (gcc, cmake, cppcheck, gcovr, doxygen)"
ADD Dockerfile /

ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC

RUN apt-get install -y graphviz
