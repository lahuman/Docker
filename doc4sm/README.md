TOMCAT 설정
==========

1. 이미지 생성

```bash
docker build --rm -t lahuman/doc4sm:centos7 . 
```

2. 생성된 이미지를 기반으로 컨테이너 생성

```bash
# 1번 TOMCAT 생성
docker run --name doc4sm1 -h lahuman --mac-address 02-42-AC-11-00-62 --link mariadb-doc4sm:mariadb -d -it -p 8080:8080 -v /home/docker/doc4sm/data:/data  --privileged=true  lahuman/doc4sm:centos7 /usr/local/apache-tomcat-8.0.21/bin/catalina.sh run

# 2번 TOMCAT 생성 
docker run --name doc4sm2 -h lahuman --mac-address 02-42-AC-11-00-62 --link mariadb-doc4sm:mariadb -d -it -p 8080:8080 -v /home/docker/doc4sm/data:/data  --privileged=true  lahuman/doc4sm:centos7 /usr/local/apache-tomcat-8.0.21/bin/catalina.sh run
```

