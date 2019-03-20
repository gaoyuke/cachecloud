#################################
#version: 1.2.1
#desc: cachecloud 镜像
#################################
FROM maven:3.6-jdk-8-alpine

MAINTAINER truman

ENV CACHECLOUD_VERSION 1.2.1
ENV base_dir /opt/cachecloud-web
WORKDIR ${base_dir}
ADD ./ /tmp/cachecloud-${CACHECLOUD_VERSION}
RUN cd /tmp/cachecloud-${CACHECLOUD_VERSION} && \
       mvn clean compile install -Plocal   && \
       mkdir -p ${base_dir}/logs && \
       cp /tmp/cachecloud-${CACHECLOUD_VERSION}/script/start.sh ${base_dir} && \
       cp /tmp/cachecloud-${CACHECLOUD_VERSION}/cachecloud-open-web/src/main/resources/cachecloud-web.conf  ${base_dir}/cachecloud-open-web-1.0-SNAPSHOT.conf
VOLUME ${base_dir}
COPY start-container.sh ${base_dir}
CMD  ["bash","start-container.sh"]
EXPOSE 9999 8585
