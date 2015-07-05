Make Docker Image
------

```bash
docker build --rm -t lahuman/nginx1.9.2 .
```

Run Container
------

```bash
docker run --name=nginx -d -it -p 8800:80 lahuman/nginx1.9.2 /bin/bash
```

Run NginX Demon
------
```bash
docker exec -it nginx /bin/bash
/usr/sbin/nginx
```

