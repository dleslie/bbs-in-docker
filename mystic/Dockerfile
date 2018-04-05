## -*- docker-image-name: "bbs/mystic" -*-

FROM debootstrap/wheezy

RUN apt-get update -q -q
RUN apt-get upgrade --yes --force-yes
RUN apt-get install libhunspell-dev less sudo byobu runit unrar curl --yes --force-yes

RUN curl http://mysticbbs.com/downloads/mys112a38_l64.rar -o /tmp/mystic.rar
RUN mkdir -p /usr/local/mystic/
RUN pushd /usr/local/mystic/;unrar e -y /tmp/mystic.rar; popd

ENTRYPOINT ["/usr/sbin/runsvdir-start"]
