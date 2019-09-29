FROM alpine

MAINTAINER iel-ferk <issam.elferkh@gmail.com>

RUN apk update && \
	apk upgrade && \
	apk add vim

ENTRYPOINT vim

# To build it.
# docker build -t ex00:1.0 .

# To run it?
# docker run --rm -it $(docker images -q ex00)
