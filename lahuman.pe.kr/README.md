NGINX AND TOMCAT SETTING
==========================

가장 마지막으로 설정된 2대의 TOMCAT과 연동할 NGINX를 설치 합니다.

SETUP
-----

1. 먼저 이미지를 생성 합니다 Dockerfile과 설정은 기본적으로 [이곳](https://github.com/lahuman/CentOS-Dockerfiles/tree/master/nginx/centos7)에서 가져왔습니다.

```bash
docker build -rm -t lahuman/home:centos7 .
```

2. 생성된 이미지를 기반으로 만들려고 하는 컨테이너를 생성 합니다.

```bash
docker run --name lahuman --link doc4sm1:doc4sm1 --link doc4sm2:doc4sm2 -d -p 80:80 -v /home/docker/lahuman.pe.kr/webapp:/webapp  --privileged=true  lahuman/home:centos7
```


