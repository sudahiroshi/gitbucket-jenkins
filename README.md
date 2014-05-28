gitbucket-jenkins
=================

Boot GitBucket and Jenkins using docker and boot2docker.

## Setup

```
~$ git clone https://github.com/sudahiroshi/gitbucket-jenkins.git
~$ cd gitbucket-jenkins
~/gitbucket-jenkins$ mkdir data
~/gitbucket-jenkins$ cd boot2docker
~/gitbucket-jenkins/boot2docker$ vargrant up
~/gitbucket-jenkins/boot2docker$ cd ../gitbucket
~/gitbucket-jenkins/gitbucket$ docker build -t sudahiroshi/gitbucket .
~/gitbucket-jenkins/gitbucket$ docker run -d -p 8000:8000 -v /share/gitbucket:/var/lib/gitbucket --name gitbucket sudahiroshi/gitbucket
~/gitbucket-jenkins/gitbucket$ cd ../jenkins
~/gitbucket-jenkins/jenkins$ docker build -t sudahiroshi/jenkins .
~/gitbucket-jenkins/jenkins$ docker run -d -p 8080:8080 -v /share/jenkins:/var/lib/jenkins --name jenkins sudahiroshi/jenkins
~/gitbucket-jenkins/jenkins$ cd ../nginx
~/gitbucket-jenkins/nginx$ docker build -t sudahiroshi/nginx .
~/gitbucket-jenkins/nginx$ docker run -d -p 80:80 --link jenkins:jenkins --link gitbucket:gitbucket sudahiroshi/nginx
```

## Access form your Web browser

Please open your Web browser, and access as follows.
Don't forget "/" at end of a line.

```
http://localhost:8080/gitbucket/
http://localhost:8080/jenkins/
```
