FROM debian:jessie
MAINTAINER Emanuele Ianni <dierre@gmail.com>

RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee /etc/apt/sources.list.d/webupd8team-java.list
RUN echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886
RUN apt-get update
RUN apt-get dist-upgrade
RUN apt-get install unzip
RUN echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 select true" | debconf-set-selections
RUN apt-get install -y oracle-java8-installer
RUN wget https://services.gradle.org/distributions/gradle-2.8-bin.zip
RUN wget http://apache.panu.it/storm/apache-storm-0.10.0/apache-storm-0.10.0.zip
RUN unzip apache-storm-0.10.0.zip 
