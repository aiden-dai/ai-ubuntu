# Docker


references:
https://docs.docker.com/install/linux/docker-ce/ubuntu/


## Uninstall old versions
Older versions of Docker were called docker, docker.io , or docker-engine. If these are installed, uninstall them:

```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```

## Update the apt package index:
```bash
$ sudo apt-get update
```


## Install packages to allow apt to use a repository over HTTPS:
```bash
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```
Add Docker’s official GPG key:

```bash
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint.

```bash
$ sudo apt-key fingerprint 0EBFCD88

pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```


## Use the following command to set up the stable repository.

```bash
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```


Update the apt package index.
```bash
$ sudo apt-get update
```

Install the latest version of Docker Engine - Community and containerd, or go to the next step to install a specific version:
```bash
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

## Check

```bash
$ docker --version
Docker version 19.03.5, build 633a0ea838
```

## registry mirrors
```bash
vi /etc/docker/daemon.json
```
Add below:
```
{
 "registry-mirrors": ["https://registry.docker-cn.com"]
}
```
or

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


