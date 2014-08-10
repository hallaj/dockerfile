# Dockerfile for rbenv
FROM ubuntu:latest
MAINTAINER Hallaj <hallajs@gmail.com>

# refresh and update the repository
RUN apt-get -qq -y update

# install packages
RUN apt-get -qq -y install git
RUN apt-get -qq -y install vim
RUN apt-get -qq -y install curl
RUN apt-get -qq -y install wget
RUN apt-get -qq -y install build-essential
RUN apt-get -qq -y install libssl-dev

# clone rbenv and ruby-build
RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
RUN git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

# configure rbenv
RUN echo 'export PATH="~/.rbenv/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc
