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
RUN unzip gradle-2.8-bin.zip
RUN wget http://downloads.typesafe.com/scala/2.11.7/scala-2.11.7.tgz?_ga=1.91452762.1131253314.1437290597 -O scala.tgz
RUN tar zxvf scala.tgz
RUN mv scala-2.11.7 scala
ENV SCALA_HOME=scala
ENV PATH=$PATH:/gradle-2.8/bin:$SCALA_HOME/bin
RUN scala -version
RUN gradle -version
