#specifying our base docker-image
FROM ubuntu:14.04

# add webupd8 repository
          RUN echo "===> add webupd8 repository..."
          RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee /etc/apt/sources.list.d/webupd8team-java.list
          RUN echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu trusty main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list
          RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EEA14886
          RUN apt-get update

          RUN echo "===> install Java"
          RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections
          RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections
          RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --force-yes oracle-java8-installer oracle-java8-set-default
          RUN echo "===> clean up..."
          RUN rm -rf /var/cache/oracle-jdk8-installer
          RUN apt-get clean 
          RUN rm -rf /var/lib/apt/lists/*
#####################################################################################
####downloading and unpacking Spark 1.6.1 [prebuilt for Hadoop 2.6+ and scala 2.10]
RUN wget http://apache.mirror.triple-it.nl/spark/spark-1.6.1/spark-1.6.1-bin-hadoop2.6.tgz
RUN tar -xzf spark-1.6.1-bin-hadoop2.6.tgz

####moving the spark root folder to /opt/spark
RUN mv spark-1.6.1-bin-hadoop2.6 /opt/spark

####exposing port 8080 so we can later access the Spark master UI; to verify spark is running …etc.
EXPOSE 8080
#####################################################################################
