# Dockerfiles


Here you will find the Jenkinsfile required to create pipelins in jenkins.


You need to install [Docker Pipeline plugin](https://plugins.jenkins.io/docker-workflow/) in jenkins to run given Jenkinsfiles.


### Jenkinsfile Desc


1) PipelineJenkinsfile :- This jenkins pipeline creates docker images and publishes to public docker hub repo vrp97/mywebapp and also shows generated url of static website hosted on Azure.


2) DSLJenkinsfile :- This pipeline gets the docker image created in first pipeline from the docker hub and creates the container and prints curl result (HTTP status 200) in the log to check whether website respondes properly or not from the container.
