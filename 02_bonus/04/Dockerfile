# Titres Game on Apache Web Server

From debian:latest

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

EXPOSE 80

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y vim
RUN apt-get install -y apache2

WORKDIR /var/www
CMD rm -rf html

COPY html /var/www/

ENTRYPOINT /bin/bash

# To build it
# docker build -t b03 .

# To run it
# docker run -it --rm  -p 8003:80 $(docker images -q b03)
