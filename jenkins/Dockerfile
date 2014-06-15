FROM ubuntu:14.04
MAINTAINER Martin Treusch von Buttlar <dockerfiles@m.t17r.de>

RUN apt-get update && apt-get install -y apt-transport-https
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 \
        --recv-keys 36A1D7869245C8950F966E92D8576A8BA88D21E9 \
 	    150FDE3F7787E7D11EF4E12A9B7D32F2D50582E6 && \
    echo deb https://get.docker.io/ubuntu docker main \
        > /etc/apt/sources.list.d/docker.list && \
    echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list
RUN mkdir /var/run/jenkins
RUN apt-get update && apt-get install -y curl lxc-docker jenkins
RUN ln -sf /usr/bin/docker.io /usr/local/bin/docker
ENV DOCKER_HOST unix:///tmp/docker.sock
EXPOSE 8080
CMD chown -R jenkins /var/lib/jenkins/ && su jenkins -c "java -Xmx1024m -jar /usr/share/jenkins/jenkins.war"
