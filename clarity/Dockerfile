FROM  laban/jdk7
MAINTAINER Feng Honglin <hfeng@tutum.co>

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y wget pwgen

ENV JAVA_HOME /usr/lib/jvm/java-7-oracle

ENV TOMCAT_VERSION 7.0.54
ENV CATALINA_HOME /tomcat

# INSTALL TOMCAT
RUN wget http://archive.apache.org/dist/tomcat/tomcat-7/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz
RUN tar zxf apache-tomcat-*.tar.gz && rm apache-tomcat-*.tar.gz && mv apache-tomcat* tomcat

ADD clarity.war /tomcat/webapps/clarity.war

ADD create_tomcat_admin_user.sh /create_tomcat_admin_user.sh
ADD run.sh /run.sh
RUN chmod +x /*.sh

EXPOSE 8080
CMD ["/run.sh"]
