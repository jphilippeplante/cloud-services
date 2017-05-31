This project is docker-compose project to quickly start a development environment with services like the one you have on your favorite cloud provider.

Included: MySQL, Redis, RabbitMQ, Eureka, Config-Server, Hystrix Dashboard and Turbine.

# Required
- Install Docker and his requirements (ex: VirtualBox).
- (Windows) Install and use a Unix shell like Git Bash, Cygwin, Docker Tools, etc.
- Administrator rights to run docker and docker-compose.

# Usage
Be sure that your docker-machine is up and running. The first start up is very long, your system needs to download the dockers images and build the custom ones with maven.

```
docker-compose up
```

Start up in background
```
docker-compose up -d
```

Start up (multiple files) :
```
docker-compose -f docker-compose.yml -f extras/service_example.yml <...> up
```

# Images
## Docker images from Docker Hub:
- mysql:latest
  - Port: 3306
  - Login: root/my-secret-pw
  - Data location: /tmp/local-mysql
- redis:alpine
  - Port: 6379
  - Data location: /tmp/local-redis
- rabbitmq:management
  - Port: 5672
  - Management port: http://<ip>:15672 u/p: guest/guest

## Custom Docker images:
- Spring Cloud Config Server (https://github.com/jphilippeplante/config-server)
  - Port: 8888
  - Configuration: configurations/config-server.yml
- Spring Cloud Eureka Server (https://github.com/jphilippeplante/eureka-server)
  - Port: 8761
  - Configuration: configurations/eureka-server.yml
- Hystrix and Turbine via rabbitMQ (https://github.com/jphilippeplante/hystrix-turbine)
  - Hystrix Dashbord: http://<ip>:7979/hystrix
  - Turbine Stream: http://<ip>:8989/turbine.stream
