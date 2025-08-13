FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Europe/Berlin

RUN apt-get update
RUN mkdir -p /home/ubuntu/Downloads

RUN apt-get install -y fish
ENV SHELL=/usr/bin/fish

RUN apt-get install -y curl git software-properties-common 

# Add deadsnakes PPA for newer Python versions
RUN add-apt-repository ppa:deadsnakes/ppa -y
RUN apt-get update
RUN apt-get install -y python3.10-dev python3.10-distutils python3-pip
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1

RUN python3 -m pip install --upgrade pip setuptools wheel
RUN python3 -m pip install mkdocs-material