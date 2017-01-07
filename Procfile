FROM ubuntu:14.04

MAINTAINER Sidesplitter, https://github.com/SexualRhinoceros/MusicBot

#Install dependencies
RUN sudo apt-get update \
    && sudo apt-get install software-properties-common -y \
    && sudo add-apt-repository ppa:fkrull/deadsnakes -y \
    && sudo add-apt-repository ppa:mc3man/trusty-media -y \
    && sudo apt-get update -y \
    && sudo apt-get install build-essential unzip -y \
    && sudo apt-get install python3.5 python3.5-dev -y \
    && sudo apt-get install ffmpeg -y \
    && sudo apt-get install libopus-dev -y \
    && sudo apt-get install libffi-dev -y
	&& sudo apt-get install software-properties-common -y
	&& sudo add-apt-repository ppa:fkrull/deadsnakes -y
	&& sudo add-apt-repository ppa:mc3man/trusty-media -y
	&& sudo apt-get update -y
	&& sudo apt-get upgrade -y
	&& sudo apt-get install build-essential unzip -y
	&& sudo apt-get install git python3.5 python3.5-dev ffmpeg libopus-dev libffi-dev libsodium-dev -y

#Install Pip
RUN sudo apt-get install wget \
    && wget https://bootstrap.pypa.io/get-pip.py \
    && sudo python3.5 get-pip.py
	&& sudo python3.5 run.py

#Add musicBot
ADD . /musicBot
WORKDIR /musicBot

#Install PIP dependencies
RUN sudo pip install -r requirements.txt
RUN sudo pip3.5 install --upgrade git+https://github.com/Rapptz/discord.py@async
RUN sudo apt-get install opus-tools

#Add volume for configuration
VOLUME /musicBot/config

CMD python3.5 run.py

WORKER: python run.py