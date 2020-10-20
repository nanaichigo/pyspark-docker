FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y openjdk-8-jdk wget

# wget
RUN wget http://ftp.riken.jp/net/apache/spark/spark-3.0.1/spark-3.0.1-bin-hadoop3.2.tgz
RUN tar zxvf spark-3.0.1-bin-hadoop3.2.tgz
RUN mv spark-3.0.1-bin-hadoop3.2 /usr/local
RUN cp -r /usr/local/spark-3.0.1-bin-hadoop3.2 /usr/local/spark

ENV SPARK_HOME /usr/local/spark
ENV PATH $PATH:$SPARK_HOME/bin

RUN apt-get install -y python3 python3-pip
RUN ln -s /usr/bin/python3 /usr/bin/python

WORKDIR $SPARK_HOME/python
RUN python setup.py install