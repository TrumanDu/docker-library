#################################
#version: 1.00
#desc: opentsdbenv镜像
#opentsdbenv
#################################
FROM openjdk:8-jdk-alpine
MAINTAINER truman


RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/community >> /etc/apk/repositories \
    && apk --update add \
       bash \
	&& apk add -U --no-cache gnuplot git  automake autoconf make python
