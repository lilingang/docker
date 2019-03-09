FROM alpine
MAINTAINER lilg <lilg@asiainfo.com>
ENV GLIBC_VERSION 2.23-r3

RUN apk add --no-cache --update-cache --update bash curl ca-certificates && \
    curl -o /tmp/glibc.apk -L "https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-${GLIBC_VERSION}.apk" && \
    curl -o /tmp/glibc-bin.apk -L "https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-bin-${GLIBC_VERSION}.apk" && \
    apk add --allow-untrusted /tmp/glibc.apk && \
    apk add --allow-untrusted /tmp/glibc-bin.apk && \   
    mkdir -p /opt/btsync && \
    rm -rf /tmp/* /var/cache/apk/* && \
    mkdir -p /btsync/data && \
    mkdir -p /btsync/conf && \
    mkdir -p /btsync/folders
ADD btsync /opt/btsync/btsync
ADD btsync.conf /btsync/conf/btsync.conf
VOLUME /btsync/folders
CMD ["/opt/btsync/btsync","--nodaemon","--config","/btsync/conf/btsync.conf","--log","/btsync/data/btsync.log"]
