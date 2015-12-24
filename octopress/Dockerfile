# minimal ruby configuration from
# https://blog.codeship.com/build-minimal-docker-container-ruby-apps/

# disclaimer: this is for an already configured git
# repository with github pages. It’s not for a fresh configuration.
# Sorry about that, this was done for my personal needs.
# If there is a need for it just ask, I’ll cook that.

# to build it run "docker build -t octopress ."
# to run it run 
# docker run -p 4000:4000 -v /Users/eianni/Documents/personal/repositories/invasionofsmallcubes.github.io/:/octopress/ -i -t --entrypoint="/bin/bash" octopress
# also remember that when you are using jekyll to check the blog run it this way
# jekyll serve --host 0.0.0.0
# so that you open the port to external vm clients

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
