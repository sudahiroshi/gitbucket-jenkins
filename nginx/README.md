# nginx by docker

## Prepare

```
$ docker build -t sudahiroshi/nginx .
```

## Boot

```
$ docker run -d -p 80:80 -link jenkins:jenkins sudahiroshi/nginx
```

## Reference


