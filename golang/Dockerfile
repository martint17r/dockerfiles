FROM debian:jessie
MAINTAINER Martin Treusch von Buttlar <dockerfiles@m.t17r.de>
RUN apt-get update && apt-get install -yq git mercurial curl

ENV PATH $PATH:/go/bin
ENV GOPATH /go
WORKDIR /go

RUN mkdir /go/bin
RUN (cd bin; curl https://godeb.s3.amazonaws.com/godeb-amd64.tar.gz | tar xz)
RUN godeb install $(godeb list | grep ^1.3 | grep -v rc | sort -nr | head -n1)
