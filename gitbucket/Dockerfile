FROM debian:stable
MAINTAINER Hiroshi Suda <suda@net.it-chiba.ac.jp>

RUN apt-get update
RUN apt-get dist-upgrade
RUN apt-get install -y curl
RUN apt-get install -q -y openjdk-7-jre-headless
#RUN apt-get install -y tomcat7
RUN mkdir /usr/share/gitbucket
RUN mkdir /var/lib/gitbucket
RUN curl -o /usr/share/gitbucket/gitbucket.war -L https://github.com/takezoe/gitbucket/releases/download/1.13/gitbucket.war

EXPOSE 8000

VOLUME ["/var/lib/gitbucket"]

CMD java -jar /usr/share/gitbucket/gitbucket.war --port=8000 --gitbucket.home=/var/lib/gitbucket --prefix=/gitbucket
