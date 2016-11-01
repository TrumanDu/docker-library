#################################
#version: 1.00
#desc: opentsdb镜像
#opentsdb Version:2.2.0
#################################
FROM openjdk:8-jdk-alpine
MAINTAINER truman

ENV TSDB_VERSION 2.2.0
RUN mkdir /opt/
WORKDIR /opt/
RUN echo http://dl-cdn.alpinelinux.org/alpine/edge/community >> /etc/apk/repositories \
    && apk --update add \
       bash \
       wget \
	  && apk add -U --no-cache gnuplot git  automake autoconf make python \
    && wget --no-check-certificate \
       -O v${TSDB_VERSION}.zip \
       https://github.com/OpenTSDB/opentsdb/archive/v${TSDB_VERSION}.zip \
    && unzip v${TSDB_VERSION}.zip \
    && rm v${TSDB_VERSION}.zip \
    && cd /opt/opentsdb-${TSDB_VERSION} \
    && ./build.sh \
    && apk del builddeps \
    && rm -rf /var/cache/apk/*

ADD script/start_opentsdb.sh /opt/opentsdb-${TSDB_VERSION}/
CMD ["bash","start_opentsdb.sh"]
EXPOSE 4242
