#Debian version for python developing environment

FROM debian:latest

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

RUN apt-get update && apt-get upgrade -y && \
	apt-get install vim git curl python3 python3-pip python3-dev -y && \
	mkdir /root/apps

WORKDIR /root/apps
ENTRYPOINT ["bash"]

# To build it
# docker build -t b02 .

# To run it
# docker run -it --rm $(docker images -q b02)