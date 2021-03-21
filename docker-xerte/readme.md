This Dockerfile builds the image needed for Xerte 3.9

The image is based on https://github.com/muggezifter/xerte_docker

Create folder USER-FILES
Download php.ini and Dockerfile

First run:
docker build --tag xerte39 .

And then:
docker run -td --name=xerte39 -p 8041:80 -v $PWD/php.ini:/usr/local/etc/php/php.ini -v $PWD/USER-FILES:/var/www/html/xerteonlinetoolkits/USER-FILES xerte39
