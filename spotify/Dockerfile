# Dockerfile
# spotify-client

FROM debian:latest

RUN  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys BBEBDCB318AD50EC6865090613B00F1FD2C19886 >/dev/null && \
      echo deb http://repository.spotify.com stable non-free > /etc/apt/sources.list.d/spotify.list && \
      apt-get -qq update && \
      apt-get -qqy install spotify-client
