FROM ubuntu:18.04
COPY ./shell/.bashrc /root/.bashrc
#COPY ./shell/sources.list /etc/apt/sources.list

RUN apt-get update
RUN apt-get install -y nginx
RUN apt-get install -y curl
RUN apt-get install -y nano
RUN apt-get install -y net-tools
RUN apt-get install -y iproute2
RUN apt-get install -y iputils-ping
RUN apt-get install -y traceroute

RUN mkdir /etc/nginx/ssl/
COPY ./config/nginx-php-ssl /etc/nginx/sites-available/default
COPY ./ssl/dhparam.pem /etc/nginx/ssl/dhparam.pem
COPY ./ssl/nginx.crt /etc/nginx/ssl/nginx.crt
COPY ./ssl/nginx.key /etc/nginx/ssl/nginx.key
COPY ./config/nginx.conf /etc/nginx/nginx.conf

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]