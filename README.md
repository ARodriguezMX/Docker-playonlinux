# Docker-playonlinux
A Dockerbuild to create a docker image with playonlinux. This fork is based on Debian Stretch.

## Installation:
```
git clone https://github.com/ARodriguezMX/Docker-playonlinux
docker build -t playonlinux <build file path>
```
Or get the image from Docker hub:
```
docker pull joriss/playonlinux
```

## Usage:
```
docker run -it --privileged -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw -v /dev/snd:/dev/snd:rw [-v <local dir for playonlinux>:/home/poluser:rw] playonlinux
```

The mount an external volume is optional, but recommended. 

## Examples of running
First time usage:
```
docker run -it --privileged --device /dev/dri/card0:/dev/dri/card0 -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw -v /dev/snd:/dev/snd:rw -v /home/user/docker/pol/:/home/poluser/:rw --name playonlinux ARdz/polstretch
```
After running for the first time:
```
docker start playonlinux
```

