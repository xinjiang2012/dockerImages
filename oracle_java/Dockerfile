FROM oraclelinux:7.5

LABEL MAINTAINER="xin_jiang@outlook.com"

RUN mkdir /tmp/downloads
COPY /resources/jdk-8u144-linux-x64.rpm /tmp/downloads
RUN cd /tmp/downloads && \
    yum install -y jdk-8u144-linux-x64.rpm && \
    rm -f jdk-8u144-linux-x64.rpm && yum clean all

RUN echo -e 'export JAVA_HOME=/usr/java/jdk1.8.0_144\nexport PATH=${JAVA_HOME}/bin:$PATH\nexport CLASSPATH=$JAVA_HOME/lib/tools.jar' >> /etc/profile
