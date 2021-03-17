# Docker에서 MariaDB 사용하기
## https://hub.docker.com/_/mariadb
참고 : url에 '_' 들어가면 공식적으로 지원해주는 이미지이다.

```docker
sudo docker run -d --name mariadb -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root1234 -e MYSQL_DATABASE=test mariadb --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
```
참고 : -d는 백그라운드로 실행

```docker
sudo docker logs -f mariadb
```

```docker
sudo docker stop mariadb
```

```docker
sudo docker stop mariadb
sudo docker rm mariadb
```
