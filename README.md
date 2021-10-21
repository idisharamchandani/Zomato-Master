## Installing and setting up docker on EC2

> Note this is just one time step please dont repeat more than once for the same EC2 instance.

### SSH to your EC2 instance

```shell
ssh -i <your key> ubuntu@<public ip>
ssh -i Zomato-clone.pem ubuntu@65.1.127.141
```

### create new app directory

```shell
mkdir app
cd app
```

### clone repository

```shell
git clone <your repo url>
```

### Go inside project directory

```shell
cd <your directory name>
```

### Now install docker

_Please run the below commands one by one._

```shell
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```shell
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu  $(lsb_release -cs)  stable"
```

```shell
sudo apt-get install docker-ce
```

Now verify docker installation

```shell
sudo docker --version
```

Now enable to docker to run when systen starts up

```shell
sudo systemctl start docker
```

```shell
sudo systemctl status docker
```
> ctrl + c won't work here, to close it type :q

### Now Install Docker Compose

_Please run the below commands one by one._

```shell
sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

```
> if this not work then only execute these

```shell
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```shell
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```shell
sudo chmod +x /usr/local/bin/docker-compose

```

> even if this not work then run these bunch of lines at once
```shell
sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
apt get install docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)"  -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo mv /usr/local/bin/docker-compose /usr/bin/docker-compose
sudo chmod +x /usr/bin/docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)"  -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose version
```

Now verify docker installation

```shell
sudo docker–compose --version
```

## Run the application

```shell
docker-compose up -d --build
```
