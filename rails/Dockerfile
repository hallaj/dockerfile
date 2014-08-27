# Dockerfile
# Hallaj's rails docker file
# Built by hallaj; for hallaj

# Use rails since it's already maintained elsewhere
FROM rails:latest
# `whoami`
MAINTAINER Muhammad Hallaj bin Subery <hallajs@gmail.com>
# Let's install basic development packages
RUN apt-get update
RUN apt-get -qqy install vim git
# Create my user on the image
RUN useradd -M -s /bin/bash hallaj
# Let's switch to the created user
USER hallaj
# I'm working from my own home
WORKDIR /home/hallaj
# $HOME should be WORKDIR :)
ENV HOME /home/hallaj
# Let's do this when the image runs
CMD ["bash"]
