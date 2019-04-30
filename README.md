This is a Dockerfile to produce an image of Jenkins with docker included. 

First build a Docker image while in the same directory as the Dockerfile 

$ docker build -t jenkins-docker .

You can then run a local instance of Jenkins ensuring you map the volume of your local docker.sock to the that of the Jenkins container:

$ docker run -d -p 49001:8080 -v $HOME/jenkins_home:/var/jenkins_home:z -v /var/run/docker.sock:/var/run/docker.sock --name jenkins jenkins-docker