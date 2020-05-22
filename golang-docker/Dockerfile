FROM golang:1.14.3-alpine3.11

#install Glide
RUN apk add --no-cache git curl openssh openssl tar gzip bash ca-certificates && \
    curl https://glide.sh/get | sh

# Install requirements
RUN apk add -U openssl curl tar gzip bash ca-certificates && \
  wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub && \
  wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/2.29-r0/glibc-2.29-r0.apk && \
  apk add glibc-2.29-r0.apk && \
  rm glibc-2.29-r0.apk


#install docker
ENV DOCKER_VERSION 1.19.03.9

RUN curl https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz | tar -xvz && \
    mv docker/docker /usr/local/bin/docker && \
    chmod +x /usr/local/bin/docker && \
    rm -r docker
