FROM quay.io/justcontainers/base:v0.10.0
MAINTAINER Gorka Lerchundi Osa <glertxundi@gmail.com>

##
## INSTALL
##

# accept terms & add custom oracle repo & install oracle java 7
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
    add-apt-repository -y ppa:webupd8team/java                                                           && \
    apt-get-min update                                                                                   && \
    apt-get-install-min oracle-java7-installer

# define env vars
ENV JAVA_HOME /usr/lib/jvm/java-7-oracle

##
## CLEANUP
##

RUN apt-cleanup && rm -rf /var/cache/oracle-jdk7-installer
