#################################
#version: 1.00
#desc: opentsdb env镜像
#
#################################
FROM openjdk:8-jdk-alpine
MAINTAINER truman

RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/community >> /etc/apk/repositories \
    && apk --update add \
       bash \
    && apk add -U --no-cache gnuplot git  automake autoconf make python \
    && rm -rf /var/cache/apk/*
