# development-environment
Docker compose to start a development environment with MySQL, Redis, Eureka, Config-Server, Geode, ...

Start up:
```
docker-compose up
```
Start up (multiple files) :
```
docker-compose -f docker-compose.yml -f orgs/organisation_example.yml <...> up
```

Start up in background
```
docker-compose up -d
```
