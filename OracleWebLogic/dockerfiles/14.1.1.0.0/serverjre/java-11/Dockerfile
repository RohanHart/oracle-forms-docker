#
# Dockerfile for creating Oracle JDK 11 Images based on OL latest
#
FROM oraclelinux:7-slim

MAINTAINER Dirk Nachbar <https://dirknachbar.blogspot.com>

ENV JAVA_PKG=jdk-11*linux-x64_bin.tar.gz \
    JAVA_HOME=/usr/java/default

ADD $JAVA_PKG /usr/java/

RUN export JAVA_DIR=$(ls -1 -d /usr/java/*) && \
    ln -s $JAVA_DIR /usr/java/latest && \
    ln -s $JAVA_DIR /usr/java/default && \
    alternatives --install /usr/bin/java java $JAVA_DIR/bin/java 20000 && \
    alternatives --install /usr/bin/javac javac $JAVA_DIR/bin/javac 20000 && \
    alternatives --install /usr/bin/jar jar $JAVA_DIR/bin/jar 20000
