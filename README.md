gitbucket-jenkins
=================

Boot GitBucket and Jenkins using docker and boot2docker.

## Setup

```
$ vargrant up
$ cd gitbucket
$ docker build -t sudahiroshi/gitbucket .
$ docker run -d -p 8000:8000 -v /share/gitbucket:/var/lib/gitbucket --name gitbucket sudahiroshi/gitbucket
$ cd ..
$ cd jenkins
$ docker build -t sudahiroshi/jenkins .
$ docker run -d -p 8080:8080 -v /share/jenkins:/var/lib/jenkins --name jenkins sudahiroshi/jenkins
$ cd ..
$ cd nginx
$ docker build -t sudahiroshi/nginx .
$ docker run -d -p 80:80 --link jenkins:jenkins --link gitbucket:gitbucket sudahiroshi/nginx
```

## Access form your Web browser

Please open your Web browser, and access as follows.
Don't forget "/" at end of a line.

```
http://localhost:8080/gitbucket/
http://localhost:8080/jenkins/
```
