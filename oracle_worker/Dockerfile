FROM oraclelinux:7.5
LABEL MAINTAINER="xin_jiang@outlook.com"

ENV REFRESHED_AT="2018-05-12 17:56"

ENV http_proxy=http://cn-proxy.jp.oracle.com:80
ENV https_proxy=http://cn-proxy.jp.oracle.com:80
ENV ftp_proxy=http://cn-proxy.jp.oracle.com:80

#install pip for default python installer
RUN curl -O https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py

#Install OCI CLI  
RUN pip install oci-cli

#OCI config files
COPY oci /root/.oci/
#ENV REQUESTS_CA_BUNDLE=/root/.oci/combined_r1.crt

#Set alias for OCI cli
RUN echo 'alias ocir1="oci --cert-bundle '/root/.oci/combined_r1.crt'"' >> ~/.bash_aliases
RUN echo ". ~/.bash_aliases" >> ~/.bashrc

#RUN curl --silent --location https://rpm.nodesource.com/setup_8.x | bash -
#RUN yum install -y -q nodejs