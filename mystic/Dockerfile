## -*- docker-image-name: "bbs/mystic" -*-

FROM ubuntu

MAINTAINER Dan <dan@ironoxide.ca>

RUN apt-get update -q -q
RUN apt-get upgrade --yes --allow-unauthenticated --allow-downgrades --allow-remove-essential --allow-change-held-packages
RUN apt-get install libhunspell-dev less sudo byobu runit unrar curl ibritish-insane ispell wbritish-insane spell --yes

RUN curl --location https://raw.githubusercontent.com/dleslie/bbs-in-docker/master/mystic/mys112a38_l64.rar -o /tmp/mystic.rar
RUN mkdir -p /usr/local/mystic/
WORKDIR /usr/local/mystic/
RUN unrar e -y /tmp/mystic.rar
RUN rm /tmp/mystic.rar
ENV PATH=/usr/local/mystic:$PATH
