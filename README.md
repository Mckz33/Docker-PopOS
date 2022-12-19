# Docker-PopOS
comandos para instalação do docker no popOS



# Installation of the Docker through the repository in Pop!_OS

```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```


Download the GPG key of the Docker from its website and add it to the repository of Pop!_OS:

```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```


Add the stable repository of the dockers from its website to the repository of Pop!_OS:

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```


Update again

```
sudo apt update
```


Install the latest version of Dockers on Pop!_OS:

```
sudo apt install docker-ce docker-ce-cli containerd.io -y
```


After the complete installation of the Docker, we will check its status using the command:

```
sudo systemctl status docker
```


See the docker version

```
docker --version
```


Install docker-compose

```
sudo apt install docker-compose -y
```


See the docker-compose version

```
docker-compose --version
```


Add group permissions

```
sudo groupadd docker
sudo gpasswd -a $USER docker
sudo setfacl -m user:$USER:rw /var/run/docker.sock
```

Test a container example

```
docker run hello-world
```
