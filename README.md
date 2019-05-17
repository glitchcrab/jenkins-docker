# jenkins-docker

Simple example of how to install Docker inside of Jenkins, mount the socket,
and use the entrypoint to give jenkins access to that socket with the docker
gid permissions.

## Alterations

 * uses jenkins:lts-slim to save on space.
 * sets Jenkins UID to 2000 to avoid collisions with system users when bind mounting the home dir.

## Usage

```
docker run -d -v /host/bind/mount:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -p 8000:8000 -p 50000:50000 analbeard/jenkins-docker:tagname
```
