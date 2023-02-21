# MysSQL Docker容器启动命令汇总

## 1、MySQL 8.0

```shell
docker run -p 9306:3306 --name mysql8 -v ./conf:/etc/mysql/conf.d -v ./logs:/logs -v ./data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql
docker exec -it mysql8 /bin/bash
mysql -u root -p
use mysql;
ALTER USER 'root'@'%' IDENTIFIED BY '123456' PASSWORD EXPIRE NEVER;
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456';
FLUSH PRIVILEGES;
exit;
CTRL + D
docker restart mysql8
```
