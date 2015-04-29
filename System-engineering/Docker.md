#Docker

## Commands
```
docker ps -a
docker rm
docker rm $(docker ps -a | awk '{print$1}')

docker rmi
docker rmi $(docker images
```

## References
#### 개인 블로그
http://www.alexecollins.com/tags/docker/

#### 한글 문서 모음
https://github.com/remotty/documents.docker.co.kr