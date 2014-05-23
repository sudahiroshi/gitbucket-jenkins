# jenkins by docker

## Prepare

```
$ docker build -t sudahiroshi/jenkins .
```

## Boot

```
$ docker run -d -p 8080:8080 -v /share/jenkins:/var/lib/jenkins sudahiroshi/jenkins
```

## Reference

[https://github.com/orchardup/docker-jenkins.git](https://github.com/orchardup/docker-jenkins.git)

