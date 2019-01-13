FROM ubuntu:18.04
COPY ./shell/.bashrc /root/.bashrc
COPY ./shell/sources.list /etc/apt/sources.list

WORKDIR /usr/src

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

RUN npm install -g create-react-app@1.5.2
RUN create-react-app app