# Apache Server on Debian

From debian:latest

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

EXPOSE 80

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y vim
RUN apt-get install -y apache2

WORKDIR /var/www/html

ENTRYPOINT /bin/bash

# To build it
# docker build -t b02 .

# To run it
# docker run -it -p 8002:80 b02
