# tomcat-deployer
This REPO would describe how to deploy WAR in Docker tomcat container.
Before starting the step, please pull the docker image from [dockerhub of tomcat](https://hub.docker.com/_/tomcat?tab=description), 
and `jdk8-openjdk-slim` would be the default tag of docker image.

```
docker pull tomcat:jdk8-openjdk-slim
```

* Step 1. Copy the war file to the `dockerfile` directory.
* Step 2. Executing the command:
```$bash
cd dockerfile
docker build -t your_name_of_dockerhub/some-app-image:version --build-arg PATH_OF_WAR=name_of_your_war ./
```
* Step 3. Start the container
```$bash
docker run -it --rm -p 8888:8080 your_name_of_dockerhub/some-app-image:version
```
* Step 4. Checking tomcat service
```$bash
http://localhost:8888/
```
* Step 5. Browse your application on browser
```$bash
http://localhost:8888/name_of_your_war/xxx.jsp
```
