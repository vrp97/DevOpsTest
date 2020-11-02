# Dockerfiles


Here you will find the Dockerfiles required to create the custom Image and you can create image from Dockerfile by below commands:


```bash
docker build -t yourCustomImageName dir/whereDockerfileResides/
docker run -it -p 8080:8080 yourCustomImageName
```


Here Simple JSP website will be hosted on tomcat server at HelloWorld link, ex. http://website:8080/HelloWorld
