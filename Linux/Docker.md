# Docker

* [Basic intro](https://docs.docker.com/get-started/)
* [Installation](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
* Additional setup (to not do sudo everytime) - `sudo usermod -aG docker <your-user>` & **logout & login**

## Common commands

```bash
## List Docker CLI commands
docker
docker container --help

## Display Docker version and info
docker --version
docker version
docker info

## Execute Docker image
docker run hello-world

## List Docker images
docker image ls

## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq
```
