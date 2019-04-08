# Dockerfile for Sphinx SE
FROM ubuntu:16.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get -y update
RUN apt-get upgrade -y

# Install useful tools
RUN apt-get -y install sphinxsearch

RUN cp /etc/sphinxsearch/sphinx.conf.sample /etc/sphinxsearch/sphinx.conf

# expose TCP port
EXPOSE 9312
EXPOSE 9306

CMD searchd --nodetach
