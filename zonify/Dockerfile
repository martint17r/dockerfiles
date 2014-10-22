FROM debian:jessie
MAINTAINER Martin Treusch von Buttlar <dockerfiles@m.t17r.de>

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y ruby ruby-nokogiri && \
    gem install zonify && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
ENV AWS_REGION eu-west-1
ENV EC2_URL ec2.eu-west-1.amazonaws.com
ENTRYPOINT ["/usr/local/bin/zonify"]
