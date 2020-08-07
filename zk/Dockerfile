FROM ubuntu:16.04

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-armhf
 
 
# install packages
RUN \
  apt-get update && apt-get install -y \
  ssh \
  rsync \
  vim inetutils-ping telnet\
  openjdk-8-jdk \
  wget libzip4 libsnappy1v5 libssl-dev && \
  rm -rf /var/lib/apt/lists/* 
  
WORKDIR /root
RUN wget http://mirrors.advancedhosters.com/apache/zookeeper/zookeeper-3.5.8/apache-zookeeper-3.5.8-bin.tar.gz \
  && tar -xvf apache-zookeeper-3.5.8-bin.tar.gz \
  && mv apache-zookeeper-3.5.8-bin /opt/zookeeper \
  && mv /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg \
  && rm -f apache-zookeeper-3.5.8-bin.tar.gz
 
WORKDIR /opt/zookeeper
EXPOSE 2181
CMD ["/opt/zookeeper/bin/zkServer.sh","start"]
