# lahuman@daum.net 

FROM centos:centos7
MAINTAINER The CentOS Project <cloud-ops@centos.org>

RUN yum -y update; yum clean all
RUN yum -y install epel-release tar ; yum clean all
#RUN yum -y install gcc-c++ zip unzip wget openssl pcre-dev pcre-devel zlib-devel make ; yum clean all
RUN yum -y install gcc gcc-c++ make zlib-devel pcre-devel openssl-devel

# if this line don't work you will manual download and continue
RUN  wget http://nginx.org/download/nginx-1.9.2.tar.gz
RUN tar -xvzf nginx-1.9.2.tar.gz

ADD run.sh /run.sh
RUN /run.sh

# first time i did it. But i don't know, Why didn't working.. So i used Shell file.
#CMD ["/bin/bash", "/run.sh"]
#CMD ["cd /nginx-1.9.2" "./configure \
#--user=nobody                          \
#--group=nobody                         \
#--prefix=/etc/nginx                   \
#--sbin-path=/usr/sbin/nginx           \
#--conf-path=/etc/nginx/nginx.conf     \
#--pid-path=/var/run/nginx.pid         \
#--lock-path=/var/run/nginx.lock       \
#--error-log-path=/var/log/nginx/error.log \
#--http-log-path=/var/log/nginx/access.log \
#--with-http_gzip_static_module        \
#--with-http_stub_status_module        \
#--with-http_ssl_module                \
#--with-pcre                           \
#--with-file-aio                       \
#--with-http_realip_module             \
#--without-http_scgi_module            \
#--without-http_uwsgi_module           \
#--without-http_fastcgi_module"]
#CMD ["cd /nginx-1.9.2", "make"]
#CMD ["cd /nginx-1.9.2", "make install"]

EXPOSE 80

CMD [ "/usr/sbin/nginx" ]
