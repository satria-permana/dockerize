FROM ubuntu:18.04
COPY ./shell/.bashrc /root/.bashrc
COPY ./shell/sources.list /etc/apt/sources.list

RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y nano
RUN apt-get install -y net-tools
RUN apt-get install -y iproute2
RUN apt-get install -y iputils-ping
RUN apt-get install -y traceroute