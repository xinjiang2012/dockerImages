FROM oraclelinux:7.5
LABEL MAINTAINER="xin_jiang@outlook.com"

ENV REFRESHED_AT="2018-05-12 16:00"

ENV http_proxy=http://cn-proxy.jp.oracle.com:80
ENV https_proxy=http://cn-proxy.jp.oracle.com:80
ENV ftp_proxy=http://cn-proxy.jp.oracle.com:80

#install pip for default python installer
RUN curl -O https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py

#Install OCI CLI  
RUN pip install oci-cli

#RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash -
#RUN yum install -y -q nodejs



