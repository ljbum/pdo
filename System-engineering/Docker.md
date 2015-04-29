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
### Blog
http://www.alexecollins.com/tags/docker/