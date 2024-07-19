# syntax=docker/dockerfile:1
FROM ubuntu:jammy-20240405
MAINTAINER Maximilian Wende <maximilian.wende@freiberginstruments.com>
LABEL Description="Image for building and debugging arm-embedded projects from git"
ADD Dockerfile /

RUN apt-get update
RUN apt-get install -y build-essential cmake gcc-arm-none-eabi
