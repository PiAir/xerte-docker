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

Add ssh file to boot partition (use wired internet!)

Boot up and wait...

Use your router to find the ip-address and note it down

## Setup Raspberry Pi

Connect to the pi using usernam: pi and password: raspberry
Change the password using 'passwd'

Run the config tool:
```
sudo raspi-config
```

Change the hostname to eg rpi4docker
```
System Options > Hostname
```
Change the GPU memory to 16MB	
```
System > Performance Options > GPU Memory > 16MB
```
Change Timezone to Amsterdam (if applicable)
```
Localisation Options > Timezone > Europe > Amsterdam
```

Exit and reboot. Reconnect to the Pi

## Install Docker and Docker-compose

Follow the instructions on: https://devdojo.com/bobbyiliev/how-to-install-docker-and-docker-compose-on-raspberry-pi

### docker
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

sudo usermod -aG docker pi
```
logout and login again as user pi. Test if docker is running properly:
```
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
