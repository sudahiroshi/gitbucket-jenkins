FROM debian:stable
MAINTAINER Hiroshi Suda <suda@net.it-chiba.ac.jp>

RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -q -y openjdk-7-jre-headless && apt-get clean
RUN curl http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list

RUN mkdir /var/run/jenkins
RUN apt-get update
RUN apt-get install -y jenkins

EXPOSE 8080

VOLUME ["/var/lib/jenkins"]

ENV JENKINS_HOME /var/lib/jenkins
CMD java -jar /usr/share/jenkins/jenkins.war --prefix=/jenkins
