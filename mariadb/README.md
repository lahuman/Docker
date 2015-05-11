[MariaDB LINK 참조](https://github.com/lahuman/CentOS-Dockerfiles/tree/master/mariadb/centos7)
===================================================================

AFTER DOING
----

/etc/my.cnf 파일을 현재 디렉토리에 있는 것으로 변경하거나 

```bash
docker exec -it <mariadb> /bin/bash
```

를 통하여 다음 인코딩 정보를 추가 한다.

```bash
[mysqld]
# 테이블 대소문자 구분 제거
lower_case_table_names=1
# 인코딩 설정
character-set-server=utf8
collation-server=utf8_general_ci
```


