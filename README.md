# AzuraBot

**AzuraBot** is a Go-powered music playing bot specifically built for the AzuraCast radio software.

Using AzuraBot, you can easily play your radio station through a voice channel on Discord.

### Installing

#### Step 1: Install Docker and Docker Compose

Your computer or server should be running the newest version of Docker and Docker Compose. You can use the easy scripts below to install both if you're starting from scratch:

```bash
wget -qO- https://get.docker.com/ | sh

COMPOSE_VERSION=`git ls-remote https://github.com/docker/compose | grep refs/tags | grep -oP "[0-9]+\.[0-9][0-9]+\.[0-9]+$" | tail -n 1`
sudo sh -c "curl -L https://github.com/docker/compose/releases/download/${COMPOSE_VERSION}/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose"
sudo chmod +x /usr/local/bin/docker-compose
sudo sh -c "curl -L https://raw.githubusercontent.com/docker/compose/${COMPOSE_VERSION}/contrib/completion/bash/docker-compose > /etc/bash_completion.d/docker-compose"
```

If you're not installing as root, you may be given instructions to add your current user to the Docker group (i.e. `usermod -aG docker $user`). You should log out or reboot after doing this before continuing below.

#### Step 2: Pull the AzuraBot Docker Compose File

Choose where on the host computer you would like AzuraBot's configuration file to exist on your server.

Inside that directory, run this command to pull the Docker Compose configuration file.

```bash
curl -L https://raw.githubusercontent.com/AzuraCast/azurabot/master/docker-compose.sample.yml > docker-compose.yml
```

#### Step 3: Customize docker-compose.yml

Open the `docker-compose.yml` file and provide the necessary variables.

#### Step 4: Run Docker Compose

From the directory that contains your `docker-compose.yml` file, run these commands:

```bash
docker-compose up -d
```
