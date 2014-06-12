FROM debian:jessie
MAINTAINER Martin Treusch von Buttlar <dockerfiles@m.t17r.de>
RUN apt-get update && apt-get install -yq golang

ENV PATH $PATH:/go/bin
ENV GOPATH /go
WORKDIR /go

