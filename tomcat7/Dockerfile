FROM laban/tomcat7:v2
MAINTAINER LabanXu "xuliuf@gmai.com"
RUN apt-get -y install tomcat7
RUN echo "JAVA_HOME=/usr/lib/jvm/java-7-oracle" >> /etc/default/tomcat7
EXPOSE 8080
CMD service tomcat7 start 
CMD tail -F /var/lib/tomcat7/logs/catalina.out
