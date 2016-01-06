simple-wildfly-app: Example Using Multiple Java EE 7 Technologies Deployed as an EAR
==============================================================================================

## Used command to generate app
mvn archetype:generate -DarchetypeGroupId=org.wildfly.archetype -DarchetypeArtifactId=wildfly-javaee7-webapp-ear-archetype -DarchetypeVersion=9.0.2.Final

## Build and Deploy to local instance
mvn clean package wildfly:deploy

## Build and create Docker Image
mvn clean package -Pdocker
docker run -it -p 8080:8080 simple-wildfly-app

## Access application locally
http://localhost:8080/simple-wildfly-app-web

## Access application in Docker Virtualbox
http://${docker-machine ip default}:8080/simple-wildfly-app-web

## Undeploy locally
mvn wildfly:undeploy

See also https://github.com/wildfly/quickstart
