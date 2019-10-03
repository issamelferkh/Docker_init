# debian version for C/C++ devlopment

From debian:latest

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y vim
RUN apt-get install -y gcc
RUN apt-get install -y build-essential git

ENTRYPOINT ["bash"]

# To build it
# docker build -t bonus01:1.0 .

# To run it
# docker run -it --rm $(docker images -q bonus01)
