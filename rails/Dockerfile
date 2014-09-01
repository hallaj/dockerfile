# Dockerfile
# Hallaj's rails docker file
# Built by hallaj; for hallaj

# Use ubuntu:latest and build our own with rbenv
# because rails:latest has errors while runing
# rails new <application>
FROM ubuntu:latest
# `whoami`
MAINTAINER Muhammad Hallaj bin Subery <hallajs@gmail.com>
# Let's install basic development packages
RUN apt-get -qq update
RUN apt-get -qqy install vim git curl wget build-essential libssl-dev
# Create my user on the image
RUN useradd -m -s /bin/bash hallaj
# Let's switch to the created user
USER hallaj
# I'm working from my own home
WORKDIR /home/hallaj
# $HOME should be WORKDIR :)
ENV HOME /home/hallaj
# Let's start building rbenv
RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
RUN git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
# Configure rbenv
RUN echo 'export PATH="~/.rbenv/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc
# Now, sadly enough; let's install ruby
# We're using ruby 2.1.2
RUN ~/.rbenv/bin/rbenv install 2.1.2
RUN ~/.rbenv/bin/rbenv local 2.1.2
RUN ~/.rbenv/bin/rbenv global 2.1.2
# Proceed with rails;
# Let's start with basic dependencies
USER root
# Begin with sqlite-dev
RUN apt-get -qqy install libsqlite3-dev
# Then we're using pgdg's repo
RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list
RUN apt-get -qqy install wget ca-certificates
RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
RUN apt-get -qq update
RUN apt-get -qqy install libpq-dev
# We're gonna use rails 4.1.5
USER hallaj
RUN ~/.rbenv/versions/2.1.2/bin/gem install rails -v 4.1.5
# Let's do this when the image runs
CMD ["bash"]
