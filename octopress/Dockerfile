# minimal ruby configuration from
# https://blog.codeship.com/build-minimal-docker-container-ruby-apps/

# disclaimer: this is for an already configured git
# repository with github pages. It’s not for a fresh configuration.
# Sorry about that, this was done for my personal needs.
# If there is a need for it just ask, I’ll cook that.

# to build it run "docker build -t octopress ."
# to run it run "docker run -d -p 127.0.0.1:80:4000 -v /Users/dierre/Projects/octopress:/root/octopress  octopress /bin/bash"

FROM debian:jessie
MAINTAINER Emanuele Ianni <dierre@gmail.com>

ENV BUILD_PACKAGES bash libcurl4-openssl-dev git
ENV RUBY_PACKAGES ruby ruby-dev bundler
ENV EXECJS_DEPENDENCY nodejs
ENV GIT_URL https://github.com/octopress/octopress.git

# Update and install all of the required packages.
# At the end, remove the apk cache
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y $BUILD_PACKAGES
RUN apt-get install -y $RUBY_PACKAGES
RUN apt-get install -y $EXECJS_DEPENDENCY
RUN rm -rf /var/cache/apk/*

# cloning octopress repo and installing version

RUN gem install --no-rdoc --no-ri pry-byebug
RUN gem install --no-rdoc --no-ri octopress-ink
RUN gem install --no-rdoc --no-ri clash 
RUN gem install --no-rdoc --no-ri octopress
RUN mkdir octopress
WORKDIR octopress
