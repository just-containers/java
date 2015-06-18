FROM quay.io/justcontainers/base:v0.9.0
MAINTAINER Gorka Lerchundi Osa <glertxundi@gmail.com>

##
## INSTALL
##

# accept terms & add custom oracle repo & install oracle java 8
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
    add-apt-repository -y ppa:webupd8team/java                                                           && \
    apt-get-min update                                                                                   && \
    apt-get-install-min oracle-java8-installer

# define env vars
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

##
## CLEANUP
##

RUN apt-cleanup && rm -rf /var/cache/oracle-jdk8-installer
