# debian version for WEB devlopment

From debian:latest

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

EXPOSE 80

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y vim
RUN apt-get install -y apache2
CMD /etc/init.d/apache2 restart

# To build it
# docker build -t bonus02:1.0 .

# To run it
# docker run -it --rm  -p 80:80 $(docker images -q bonus02)
