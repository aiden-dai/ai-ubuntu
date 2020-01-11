# Docker
Install Docker on Ubuntu

References: https://docs.docker.com/install/linux/docker-ce/ubuntu/


## Install
Run bash
```bash
# Install packages to allow apt to use a repository over HTTPS:
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

# Add Docker’s official GPG key:
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# Use the following command to set up the stable repository.
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

# Update the apt package index.
$ sudo apt-get update


# Install the latest version of Docker Engine - Community and containerd, or go to the next step to install a specific version:
$ sudo apt-get install docker-ce docker-ce-cli containerd.io

# Verify
$ docker --version
Docker version 19.03.5, build 633a0ea838
```


## Add registry mirrors
```bash
sudo vi /etc/docker/daemon.json
```
Add below:

```
{
    "registry-mirrors": ["http://hub-mirror.c.163.com"]
}
```

```bash
sudo service docker restart
```

check registry:
```bash
sudo docker info
```

Check speed
```bash
sudo docker run hello-world
```


