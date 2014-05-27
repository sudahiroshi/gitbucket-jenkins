# Docker by docker

## Prepare

```
$ docker build -t sudahiroshi/gitbucket .
```

## Boot

```
$ docker run -d -p 8000:8000 -v /share/gitbucket:/var/lib/gitbucket --name gitbucket sudahiroshi/gitbucket
```

## Reference


