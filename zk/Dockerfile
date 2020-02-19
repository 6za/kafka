FROM base-java 
WORKDIR /root
RUN wget http://mirrors.advancedhosters.com/apache/zookeeper/zookeeper-3.5.7/apache-zookeeper-3.5.7-bin.tar.gz \
  && tar -xvf apache-zookeeper-3.5.7-bin.tar.gz \
  && mv apache-zookeeper-3.5.7-bin /opt/zookeeper \
  && mv /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg \
  && rm -f apache-zookeeper-3.5.7-bin.tar.gz
 
WORKDIR /opt/zookeeper
EXPOSE 2181
CMD /opt/zookeeper/bin/zkServer.sh start
