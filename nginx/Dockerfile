FROM debian:stable
MAINTAINER Hiroshi Suda <suda@net.it-chiba.ac.jp>

RUN apt-get update
#RUN apt-get install -y curl
RUN apt-get install -y nginx && apt-get clean
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf
ADD default /etc/nginx/sites-enabled/default
ADD run /root/run
RUN chmod 755 /root/run

VOLUME [ "/var/log/nginx" ]

WORKDIR /etc/nginx

CMD [ "/root/run" ]

EXPOSE 80
EXPOSE 443

