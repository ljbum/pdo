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
### Links
#### 개인 블로그
http://www.alexecollins.com/tags/docker/
http://crosbymichael.com/category/docker.html

#### 한글 문서 모음
https://github.com/remotty/documents.docker.co.kr