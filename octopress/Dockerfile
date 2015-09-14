# minimal ruby configuration from
# https://blog.codeship.com/build-minimal-docker-container-ruby-apps/

# disclaimer: this is for an already configured git
# repository with github pages. It’s not for a fresh configuration.
# Sorry about that, this was done for my personal needs.
# If there is a need for it just ask, I’ll cook that.

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
WORKDIR ~
RUN git clone $GIT_URL octopress
WORKDIR octopress
RUN gem install --no-rdoc --no-ri pry-byebug
RUN gem install --no-rdoc --no-ri octopress-ink
RUN gem install --no-rdoc --no-ri clash 
RUN gem install --no-rdoc --no-ri octopress
