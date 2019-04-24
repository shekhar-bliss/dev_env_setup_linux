# Setup - Applications

$ = Non Root User

&#35; = Root User


#### Update Linux machine.
```
$ sudo apt update
$ sudo apt upgrade
```


#### Install Docker.
1. Install packages to allow apt to use a repository over HTTPS:
```
$ sudo apt install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

2. Add Docker’s official GPG key:
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Verify fingerprint
```
$ sudo apt-key fingerprint 0EBFCD88

pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
```

3. Select the channel to use: Stable
```
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

4. Update apt sources and install DOCKER CE
```
$ sudo apt update
$ sudo apt install docker-ce docker-ce-cli containerd.
```

a. List the versions available in your repo:
```
$ apt-cache madison docker-ce
```
b. Install a specific version
```
$ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```

5. Verify that Docker CE is installed correctly by running the hello-world image.
```
$ sudo docker run hello-world
```
----------------------------------------------------------------


#### Uninstall Docker.
1. Uninstall the Docker CE package:
```
$ sudo apt purge docker-ce
```

2. Images, containers, volumes, or customized configuration files on your host are not automatically removed. To delete all images, containers, and volumes:
```
$ sudo rm -rf /var/lib/docker
```
