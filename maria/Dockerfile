FROM mariadb:10.3.11

COPY ./shell/.bashrc /root/.bashrc

ENV MYSQL_ROOT_PASSWORD P@ssw0rd
ENV MYSQL_DATABASE initDB
ENV MYSQL_USER user
ENV MYSQL_PASSWORD password

RUN apt-get update
RUN apt-get install -y nano
RUN apt-get install -y net-tools
RUN apt-get install -y iproute2
RUN apt-get install -y iputils-ping
RUN apt-get install -y traceroute