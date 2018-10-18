FROM oraclelinux

LABEL MAINTAINER="xin_jiang@outlook.com"

# Enable SSH service
RUN yum -y install openssh-server && yum clean all
RUN mkdir /var/run/sshd
## Suppress error message 'Could not load host key: ...'
RUN /usr/bin/ssh-keygen -A

RUN echo 'root:oracle' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

#Install supervisor and copy config files
RUN cd  && \
    wget https://bootstrap.pypa.io/ez_setup.py -O - | python && \
    easy_install supervisor

RUN mkdir -p /etc/supervisor/conf.d
COPY /config/supervisord.conf /etc/supervisor/
COPY /config/supervisord-sshd.conf /etc/supervisor/conf.d/

EXPOSE 22
CMD [ "/usr/bin/supervisord", "-c", "/etc/supervisor/supervisord.conf" ]