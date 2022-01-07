# Jenkins docker setup

The files in this folder define the setup of the Jenkins master machine.  
Based on code from http://bitbucket/projects/INF/repos/jenkins-casc/browse/master

## Setup and running

It can be setup and run locally using the following commands:

To build the container from the files:

```
docker build -t miradajenkins:<version> .
```

This will create a new image tagged with the name miradajenkins:<version> based on the files in '.'

To run the container:

```
docker run -–rm -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home -–name jenkins<version> miradajenkins:<version>
```

This will start the container called jenkins<version> based on the image miradajenkins:<version>, mapping ports 8080 and 50000 on it to the local ports.  It will set up an access volume called jenkins_home on /var/jenkins_home (although that doesn't currently appear to work).  When the container is stopped it will be destroyed due to the '--rm'.

To stop and destroy the container:

```
docker stop jenkins<version>
```

