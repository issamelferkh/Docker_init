FROM debian

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

ENV TS3SERVER_LICENSE=accept

WORKDIR /home/teamspeak

EXPOSE 9987/udp 10011/tcp 30033/tcp

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y wget bzip2 && \
    wget https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.9.1.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

# 9987 default voice
# 10011 server query
# 30033 file transport

# To build it.
# docker build -t ex01 .

# To run it?
# docker run --rm -it -p 9987:9987/udp -p 10011:10011/tcp -p 30033:30033/tcp $(docker images -q ex01)
