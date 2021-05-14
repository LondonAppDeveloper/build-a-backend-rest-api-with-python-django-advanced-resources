# Deployment


## Server Setup

Use the below commands to configure the EC2 virtual machine running Amazon Linux 2.

Install Git:

```sh
sudo yum install git -y
```

Install Docker, make it auto start and give `ec2-user` permissions to use it:

```sh
sudo amazon-linux-extras install docker -y
sudo systemctl enable docker.service
sudo systemctl start docker.service
sudo usermod -aG docker ec2-user
```

Note: After running the above, you need to logout by typing `exit` and re-connect to the server in order for the permissions to come into effect.

Install Docker Compose:

```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```


## Creating an SSH Deploy Key

To create a new SSH key which can be used as the deploy key, run the command below:

```sh
ssh-keygen -t ed25519 -b 4096
```

Note: This will create a new `ed25519` key, which is the recommended key for GitHub.

To display the public key, run:

```sh
cat ~/.ssh/id_ed25519.pub
```

