# Infinite Mario Game on Nginx

From debian:latest

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

EXPOSE 80

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y vim
RUN apt-get install -y nginx

WORKDIR /var/www
CMD rm -rf html

COPY html /var/www/html

ENTRYPOINT /bin/bash

# To build it
# docker build -t b05 .

# To run it
# docker run -it -p 8005:80 b05