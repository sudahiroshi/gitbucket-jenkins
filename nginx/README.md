# nginx by docker

## Prepare

```
$ docker build -t sudahiroshi/nginx .
```

## Boot

```
$ docker run -d -p 80:80 --link jenkins:jenkins --link gitbucket:gitbucket sudahiroshi/nginx
```

## Check

```
$ docker run -i -t -p 80:80 --link jenkins:jenkins --link gitbucket:gitbucket sudahiroshi/nginx /bin/bash
root@85a04ee60b6e:/root/run &
```

## Reference


