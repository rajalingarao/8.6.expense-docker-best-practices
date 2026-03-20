* This repository created for expense project. We have frontend with nginx server, backend with nodejs server, db with mysql server. 

* We are running mysql, backend, frontend images in one server. 
Login into backend server:
```
apt update
```
```
apt install default-mysql-client
```
```
mysql -h mysql -u root -pExpenseApp@1
```

# Installing Expense Docker:
* creating docker images
```
for i in mysql backend frontend ; do cd $i ; docker build -t $i:v1.1 . ; cd ..; done

```

```
docker build -t mysql:v1.1 .
```

```
docker build -t backend:v1.1 .
```

```
docker build -t frontend:v1.1 .

```

```
docker build -t debug:v1.1 .

```

```
docker images

```

*  creating the docker network
```
docker network create expense
```

* running docker images

```
docker run -d -p 3306:3306 --name mysql --network expense mysql:v1.1

```

```
docker run -d -p 8080:8080 --name backend --network expense backend:v1.1

```

```
docker run -d -p 80:80 --name frontend --network expense frontend:v1.1

```

```
docker ps -a

```



