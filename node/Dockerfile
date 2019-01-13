FROM ubuntu:18.04
COPY ./shell/.bashrc /root/.bashrc
COPY ./shell/sources.list /etc/apt/sources.list

WORKDIR /usr/src/app

RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y nano
RUN apt-get install -y net-tools
RUN apt-get install -y iproute2
RUN apt-get install -y iputils-ping
RUN apt-get install -y traceroute
RUN apt-get install -y gnupg

RUN curl -sL https://deb.nodesource.com/setup_10.x -o nodesource_setup.sh
RUN chmod +x nodesource_setup.sh
RUN ./nodesource_setup.sh
RUN apt-get install -y nodejs

COPY package*.json ./
RUN npm install

RUN npm install nodemon -g