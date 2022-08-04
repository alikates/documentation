---
title: Install Docker Engine
author: wale soyinka
---


The Docker Engine can be used running native Docker style container workloads on Rocky Linux servers. This is sometimes preferred to running the full Docker Desktop environment.

# Add the docker repository

Use the dnf utility to add the docker repository to your Rocky Linux server. Type:

```
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

# Install the needed packages

Install the latest version of Docker Engine, containerd, and Docker Compose , type:

```
sudo dnf -y install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

# Start the systemd docker service (dockerd) and enable it for automatric startup

Use the `systemctl` utility to configure the dockerd daemon to automatically startup with the next system reboot and simultanously start it for the current session. Type:

```
sudo systemctl --now enable docker
```


## Notes

```
docker-ce       : This package provides the underlying technology for building and running docker containers (dockerd) 
docker-ce-cli           :  Provides the command line interface (CLI) client docker tool (docker)
containerd.io : Provides the container runtime (runc)
docker-compose-plugin           :  A plugin that provides the 'docker compose' subcommand 

```


