# Dockyard
`Dockerfile`s I use for work, development and fun.

## Useful images to be based on

* [Alpine Linux](https://github.com/gliderlabs/docker-alpine) image
* [Python](https://hub.docker.com/_/python/) images from the docker [registry hub](https://hub.docker.com/)

## Cheatsheet

### Bootstrapping procedure (Mac)

```
$ docker-machine start default
Starting VM...
Started machines may have new IP addresses. You may need to re-run the `docker-machine env` command.

$ docker-machine env default
export DOCKER_TLS_VERIFY="1"
export DOCKER_HOST="tcp://XXX.XXX.XX.XXX:2376"
export DOCKER_CERT_PATH="/Users/mriello/.docker/machine/machines/default"
export DOCKER_MACHINE_NAME="default"
# Run this command to configure your shell:
# eval "$(docker-machine env default)"

$ eval "$(docker-machine env default)"
```

Now we can use the terminal to run `docker` commands.

### Throw-away containers
These can be very useful in development to have custom potted environments. For example:
```
$ docker run -i -t --rm python:2.7
Python 2.7.9 (default, Jan 28 2015, 01:38:45)
[GCC 4.9.1] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> 1 + 1
2
```
This creates interactive (`-i`) Python container attached to the terminal (`-t`) that will be removed once we quit the session (`--rm`).


### Cleaning up
We can remove all containers by running:

```
$ docker rm $(docker ps -aq)
202c5f3e482e
93112fa2ad87
```

We can remove all "incompletely built" images by running:

```
$ docker images | grep none | awk '{print "docker rmi " $3;}' | sh
```

It would be probably good to add these to my dotfiles.
