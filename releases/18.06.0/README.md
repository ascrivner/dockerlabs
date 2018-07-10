# What's New Upcoming under Docker 18.06 Release?


## Feature #1: Support of "Init" for ```docker stack``` & ```compose file format v3.7```?

```
docker service create --init  --name myserve --publish 81:81 nginx:alpine
```

```
q51j4pzcb59r        myserve               replicated          1/1                 nginx:alpine                      *:81->81/tcp
```

```
[root@docker-1 ~]# docker ps | grep ngin
3ed05af29d10        nginx:alpine        "nginx -g 'daemon of…"   25 minutes ago      Up 25 minutes         80/tcp               myserve.1.ohvdi9dicxx2b460t12fdkwjy
[root@docker-1 ~]# docker exec -it 3ed0 sh
/ # ps -aef
PID   USER     TIME   COMMAND
    1 root       0:00 /dev/init -- nginx -g daemon off;
    6 root       0:00 nginx: master process nginx -g daemon off;
    7 nginx      0:00 nginx: worker process
   13 root       0:00 sh
   19 root       0:00 sh
   26 root       0:00 sh
   31 root       0:00 ps -aef
 ```
 
 ## Feature #2: DOCKER_BUILDKIT=1
