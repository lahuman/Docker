# "ported" by Adam Miller <maxamillion@fedoraproject.org> from
#   https://github.com/fedora-cloud/Fedora-Dockerfiles
#
# Originally written for Fedora-Dockerfiles by
#   scollier <scollier@redhat.com>

FROM centos:centos7
MAINTAINER The CentOS Project <cloud-ops@centos.org>

RUN yum -y update; yum clean all
RUN yum -y install epel-release tar ; yum clean all

ADD apache-tomcat-8.0.21 /usr/local/apache-tomcat-8.0.21
ADD jdk1.8.0_40 /usr/local/jdk1.8.0_40
#CMD ["tar xvfz /usr/local/jdk-8u40-linux-x64.tar.gz -C /usr/local/", "tar xvfz /usr/local/apache-tomcat-8.0.21.tar.gz -C /usr/local/" ] 
#RUN tar xvfz /usr/local/apache-tomcat-8.0.21.tar.gz -C /usr/local/ 

ADD server.xml /usr/local/apache-tomcat-8.0.21/conf/server.xml

ENV JAVA_HOME /usr/local/jdk1.8.0_40

RUN mkdir /data

EXPOSE 8080
EXPOSE 8009

VOLUME /data

#CMD ["/bin/bash", "/usr/local/apache-tomcat-8.0.21/bin/startup.sh" ]
