# spring-boot-oauth2 

```xml
-Dspring.profiles.active=default,dev
```

use Cookies convenience methods in xhr:

```xml
application-dev.yml
spring:
  profiles:
    active: dev
    include: default
```
    
#### Use different annotation @EnableOAuth2Client.
#### To remove the @EnableOAuth2Sso and replace it with the lower level annotation

#### Manual Configuration of OAuth2 Client
```java
@EnableOAuth2Client
```
Convert the application.yml to a slightly new format,
 where the prefix for configuration is facebook instead of security.oauth2:
 
## Run the Project
#### Run our goals like this for the Unix system:
```xml
 ./mvnw clean install
```
#### The following command for Batch:
```xml
 ./mvnw.cmd clean install
```
#### Run our Spring-Boot project:
```xml
 ./mvnw spring-boot:run
```
 
 
## Docker Maven Plugin
Add the plugin to the POM file
https://github.com/spotify/docker-maven-plugin
 
```xml
 docker ps //show all running container
 docker images // show all images 
```
  
 ### Run the docker build
```xml
 docker:build
 or
 mvn clean package docker:build
```
 ### Run the container useing the built image
```xml
  docker run -it - p 9999:8080 <image-name>
```
------
 
## Build a Docker Image with Maven without adding plugin to pom.xml file
```xml
$ ./mvnw com.google.cloud.tools:jib-maven-plugin:dockerBuild -Dimage=springio/OAuth2-SSO
```
To push to a Docker registry you use the build goal, instead of dockerBuild
```xml
$ ./mvnw com.google.cloud.tools:jib-maven-plugin:build -Dimage=springio/OAuth2-SSO
```

## Using Spring Profiles
##### Passing an environment variable to the Docker run command
```java
$ docker run -e "SPRING_PROFILES_ACTIVE=prod" -p 8080:8080 it OAuth2-SSO
```
## Debugging the application in a Docker container
```java
$ docker run -e "JAVA_OPTS=-agentlib:jdwp=transport=dt_socket,address=5005,server=y,suspend=n" -p 8080:8080 -p 5005:5005 -t springio/OAuth2-SSO
```


#### Another ref:

1. https://github.com/ahmed82/spring-boot-oauth2.git
2. https://medium.com/swlh/dockerizing-spring-boot-application-df5ae7dd1e37

