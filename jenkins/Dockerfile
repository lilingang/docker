FROM jenkins:alpine
MAINTAINER lilg <lilg@asiainfo.com>

USER root
RUN apk add --no-cache --update-cache --update docker  && \
    rm -rf /tmp/* /var/cache/apk/* 

RUN addgroup jenkins docker

USER jenkins
