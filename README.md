# jenkins

## Contents
This Jenkins image has the following:
- Latest Jenkins LTS
- OpenJDK 8
- Maven 3
- Nano
- Git
- Minimal plugins to get CI process started

## Pre-installed Jenkins plugins
- Maven Integration
- Docker and Docker Slaves
- Build Pipeline
- Config File Provider
- Console Column
- Copy to Slave
- Extra Columns
- Favorite
- Folder
- Git
- HTML Publisher
- Javadoc
- Workflow Aggregator
- Docker Build Step

## Build from Dockerfile
1. Run command: `docker build -t thetestguys/slumber-docker .`

## How to run
1. Pull the docker image: `docker pull thetestguys/slumber-docker`
2. Run with this command: `docker run -d -p 8080:8080 -p 50000:50000 -v <volume>/jenkins:/var/jenkins_home thetestguys/slumber-docker`

## Jenkins global tool configuration
Jenkins global tools are not configured by default. After container is started, supply these variables in Jenkins > Global Tool Configuration:
* JDK > JAVA_HOME: /usr/lib/jvm/java-8-openjdk-amd64
* Maven > MAVEN_HOME: /opt/maven

## Additionals
* Notice that plugins.txt should not have any empty line at the end of file (especially when building in Windows)
* Included is a docker-compose.yml which starts up this Jenkins image and a Selenium Grid setup (a hub, a Firefox node and a Chrome node)
