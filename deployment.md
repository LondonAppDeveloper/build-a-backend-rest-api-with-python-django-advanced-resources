# Deployment

## Create an SSH Key

To create a new `ed25519` key, use the command below:

```sh
ssh-keygen -t ed25519 -b 4096
```

## Server Setup

Use the below commands to configure the EC2 virtual machine running Amazon Linux 2.

Install Git:

```sh
sudo yum install git
```

Install Docker, make it auto start and give `ec2-user` permissions to use it:

```sh
sudo amazon-linux-extras install docker
sudo systemctl enable docker.service
sudo systemctl start docker.service
sudo usermod -aG docker ec2-user
```

Install Docker Compose:

```sh

```

# Install Git
sudo yum install git

# Install Docker

```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
