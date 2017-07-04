# Bamboo Docker Agent
This agent is tested on Atlassian Bamboo version 5.12.3.1. The official [bamboo-java-agent](https://hub.docker.com/r/atlassian/bamboo-java-agent/) is built with Java v7 but v8 is required by later versions of Bamboo server so new bootstrap files can be updated.

## Building
```bash
docker build -t bamboo-agent .
```

## Running
The official guide suggests using the path http://hostname:8085/bamboo for BAMBOO_SERVER but it never worked against my server instance. It might be the way it was setup but if it doesn't work for you then try using that.
### Simple
```bash
docker run -e HOME=/root/ -e BAMBOO_SERVER=http://hostname:8085  -it bamboo-agent
```

### Attaching docker from host
The following command allows you to execute docker commands from the container's host meaning you do not need to install docker on the agent.
```bash
docker run -e HOME=/root/ -e BAMBOO_SERVER=http://hostname:8085 -v /usr/bin/docker:/usr/bin/docker -v /usr/bin/docker-compose:/usr/bin/docker-compose -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker/aufs:/var/lib/docker/aufs -v /var/lib/docker:/var/lib/docker -it bamboo-agent
```
