# Quick and tiny Golang Container to run the gotour package by default. If run
# on a local machine without publishing ports, the webpage will be accessible by
# the IP of the Container found using `docker inspect <container>`.

FROM ubuntu:latest
MAINTAINER Nate Tangsurat <e4r7hbug@gmail.com>

RUN apt update && \
    apt install -y \
        git \
        golang \
        golang-go.tools \
        && \
    apt-get autoremove && \
    apt-get clean

ENV GOPATH="/opt/go/"
RUN go get golang.org/x/tour/gotour

EXPOSE 3999
CMD ["/bin/sh", "-c", "$GOPATH/bin/gotour -http=0:3999"]
