# LICENSE UPL 1.0
#
# Copyright (c) 2015 Oracle and/or its affiliates. All rights reserved.
#
FROM ubuntu:latest

ENV JAVA_PKG=jdk-8u172-linux-x64.tar.gz \
    JAVA_HOME=/usr/java/default \
    LANG=ja_JP.UTF-8

ADD $JAVA_PKG /usr/java/

RUN export JAVA_DIR=$(ls -1 -d /usr/java/*) && \
    ln -s $JAVA_DIR /usr/java/latest && \
    ln -s $JAVA_DIR /usr/java/default && \
    update-alternatives --install /usr/bin/java java $JAVA_DIR/bin/java 20000 && \
    update-alternatives --install /usr/bin/javac javac $JAVA_DIR/bin/javac 20000 && \
    update-alternatives --install /usr/bin/jar jar $JAVA_DIR/bin/jar 20000 && \
    apt-get update && \
    apt-get -y install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common \
    language-pack-ja-base language-pack-ja && \
    locale-gen ja_JP.UTF-8 \
