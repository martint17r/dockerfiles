FROM mtvb/golang
RUN DEBIAN_FRONTEND=noninteractive apt-get -q update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -qy git nodejs nodejs-legacy npm \
                                                       sudo zopfli mercurial
RUN adduser --home /home/build build 
RUN usermod --append --groups sudo build
RUN echo "build ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
ENV HOME /home/build
WORKDIR /js
RUN chmod og+rw /js
USER build
RUN sudo npm install -g bower grunt-cli

