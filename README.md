# Spring-Boot-
Demo Spring Boot Projects

To run this jenkins file on dockerized container

1.  docker run --name jenkins-blueocean --rm --detach  --network jenkins --env DOCKER_HOST=unix:///var/run/docker.sock --env DOCKER_CERT_PATH=/certs/client /
    --publish 8080:8080 --publish 50000:50000 --volume jenkins-data:/var/jenkins_home --volume jenkins-docker-certs:/certs/client:ro / 
    --volume /var/run/docker.sock:/var/run/docker.sock jenkinsci/blueocean/
    
2. if it say permission denied for docker.sock and sudo is not available
 2.a docker ps -a # get running container id
 2.b docker exec -u root -t -i container_id /bin/bash
 2.c chmod 666 /var/run/docker.sock
