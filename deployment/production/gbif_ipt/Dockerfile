FROM tomcat:8.5-jre8-alpine
MAINTAINER Dimas Ciputra <dimas@kartoza.com>
RUN echo "ipv6" >> /etc/module
RUN apk add --update curl && \
    apk add --update unzip && \
    apk add --update vim && \
    rm -rf /var/cache/apk/*
RUN mkdir -p /usr/local/tomcat/webapps/ipt \
    && mkdir -p /usr/local/ipt \
    && curl -Ls -o ipt.war http://repository.gbif.org/content/groups/gbif/org/gbif/ipt/2.3.5/ipt-2.3.5.war \
    && unzip -d /usr/local/tomcat/webapps/ipt ipt.war \
    && rm ipt.war
EXPOSE 8080
RUN echo "/usr/local/ipt" > /usr/local/tomcat/webapps/ipt/WEB-INF/datadir.location
CMD ["catalina.sh", "run"]