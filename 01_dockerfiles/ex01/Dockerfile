FROM debian

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

EXPOSE 9987/udp 10011/tcp 30033/tcp

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y wget bzip2 && \
    wget http://dl.4players.de/ts/releases/3.0.13.4/teamspeak3-server_linux_amd64-3.0.13.4.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.0.13.4.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

# To build it.
# docker build -t ex01:1.0 .

# To run it?
# docker run --rm -p 9987:9987/udp -p 10011:10011/tcp -p 30033:30033/tcp $(docker images -q ex01)