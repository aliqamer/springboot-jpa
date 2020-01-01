# springboot-jpa
this example runs spring-data jpa in docker container and connect with mysql database running in separate docker

mysql + spring boot api + docker

> docker pull mysql:5.6
run mysql docker container
> docker run --name mysql-standalone -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=test -e MYSQL_USER=user -e MYSQL_PASSWORD=password -d mysql:5.6


build spring boot jar
> mvn clean install
build docker image
> docker build . -t users-mysql
run spring boot application
> docker run -p 8086:8086 --name users-mysql --link mysql-standalone -d users-mysql
check if running
> docker container ls
check logs
> docker logs users-mysql
to stop
> docker stop users-mysql
remove container
> docker rm users-mysql
> docker rm mysql-standalone

http://192.168.99.100:8086/all/create
http://192.168.99.100:8086/all/
