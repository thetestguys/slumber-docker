# slumber-docker
Basic job and configuration to start slumber from jenkins

## How to use
1. Pull the docker image:

  `docker pull thetestguys/slumber-docker`

2. Run with this command:

  `docker run -d -p 8080:8080 -p 50000:50000 -v <volume>/jenkins:/var/jenkins_home thetestguys/slumber-docker`
  
3. Run these docker commands to setup basic job and config:
    `docker cp config.xml`

    `<container_name>:/var/jenkins_home`

    `docker cp hudson.tasks.Maven.xml`

    `<container_name>:/var/jenkins_home`

    `docker exec -d <container_name> mkdir`

    `/var/jenkins_home/jobs/build_slumber`

    `docker cp build_slumber/config.xml`

    `<container_name>:/var/jenkins_home/jobs/build_slumber/config.xml`

    `docker exec -d <container_name> curl -X POST http://localhost:8080/restart`

## Jenkins global tool configuration
The commands above setup the Java and Maven in Jenkins container. The default locations are:
* JDK > JAVA_HOME: /usr/lib/jvm/java-8-openjdk-amd64
* Maven > MAVEN_HOME: /opt/maven
