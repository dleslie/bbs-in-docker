## -*- docker-image-name: "bbs-mystic" -*-

FROM ubuntu:16.04

MAINTAINER Dan <dan@ironoxide.ca>

RUN apt-get update -q -q
RUN apt-get upgrade --yes --allow-unauthenticated --allow-downgrades --allow-remove-essential --allow-change-held-packages
RUN apt-get install libhunspell-dev build-essential less unrar unzip p7zip-full curl ibritish-insane ispell wbritish-insane spell libpython2.7 --yes

WORKDIR /
RUN curl --location https://raw.githubusercontent.com/dleslie/bbs-in-docker/master/mystic/mystic-112a38.x86-64.tar.xz --output - | tar Jx

WORKDIR /tmp
RUN curl --location https://raw.githubusercontent.com/dleslie/bbs-in-docker/master/cl3431.zip -o cl.zip
RUN mkdir -p /tmp/cl
WORKDIR /tmp/cl
RUN unzip -a /tmp/cl.zip
RUN make shared
RUN install -g users libcl.so.3.4.3 /usr/lib/libcl.so.3.4.3
RUN ln -s /usr/lib/libcl.so.3.4.3 /usr/lib/libcl.so
WORKDIR /
RUN rm -rf /tmp/cl*

WORKDIR /usr/local/mystic
ENV PATH=/usr/local/mystic:$PATH

EXPOSE 23
