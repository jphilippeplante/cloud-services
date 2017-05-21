# development-environment
Docker compose to start a development environment with MySQL, Redis, Eureka, Config-Server, Geode, ...

Start up:
```
docker-compose up
```

Start up in background
```
docker-compose up -d
```

Using gfsh
```
docker exec -it <locator_container_id> gfsh
gfsh>connect --locator=locator[10334]
```
