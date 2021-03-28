# xerte-docker (on Raspberry Pi)
Repository with files needed to run Xerte on Docker. First version aimed specifically at Raspberry Pi4

Note: I am not affiliated with the Xerte project and/or Docker!

### IMPORTANT !!
Although the Dockerfile works if you download it from github, the build version on Dockerhub does not yet work on Raspberry Pi4. This is because I have not setup multi-architecture build correctly for Dockerhub to automatically build other versions than the default amd64 one.


## Preparing the Raspberry pi
Goto: https://www.raspberrypi.org/software/

Goto: https://www.raspberrypi.org/software/operating-systems/

Download: https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-01-12/2021-01-11-raspios-buster-armhf-lite.zip

Install: https://www.balena.io/etcher/

Add ssh file and wpa_supplicant.conf to boot partition

Boot up and wait...

Use your router to find the ip-address and note it down

## Install Docker and Docker-compose

Follow the instructions on: https://devdojo.com/bobbyiliev/how-to-install-docker-and-docker-compose-on-raspberry-pi

### docker
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

sudo usermod -aG docker pi
docker --version
docker run hello-world
```
### docker compose
```
sudo apt-get install libffi-dev libssl-dev
sudo apt install python3-dev
sudo apt-get install -y python3 python3-pip
sudo pip3 install docker-compose

docker-compose --version

mkdir docker
cd docker
mkdir mariadb
mkdir mariadb/data
mkdir xerte
mkdir xerte/USER-FILES
```

Download the files from the repository and follow run instructions for MariaDB container and Xerte container.

Run the /setup.php
