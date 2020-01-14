

# Assignment: Manage Multiple Containers

  

* Run **nginx**, a **mysql**, and a **httpd** server
* Run all of them `--detach`, name with a `--name`
* Nginx should listen on `80:80`, httpd on `8080:80`, mysql on `3306:3306`
* When running mysql, use the `--env` option to pass in `MYSQL_RANDOM_ROOT_PASSWORD=yes` 

## Answer
```
# nginx
docker run --name nginx-test -p 80:80 -d nginx

# apache
docker run --name apache-test -p 8080:80 -d httpd

# mysql
docker run --name mysql-test -p 3306:3306 -d -e MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
```
