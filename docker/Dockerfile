#################################
#version: 1.2
#desc: cachecloud 镜像
#################################
FROM maven:3.6-jdk-8-alpine

MAINTAINER yuke

ADD cachecloud-open-web-1.0-SNAPSHOT.war cachecloud-open-web-1.0-SNAPSHOT.war
CMD ["java","-jar","cachecloud-open-web-1.0-SNAPSHOT.war"]
EXPOSE 9999 8585
