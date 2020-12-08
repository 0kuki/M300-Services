# Docker Wordpress mit DB

## Apache Container
1. ```cd /vagrant/web```
2. ```sudo apt install apache 2```
3. ```docker run --rm -d -p 8080:80 -v `pwd`/web:/var/www/html --name apache apache```
4. Kurz testen mit: ```curl http://localhost:8080```
   
## MySQL Container

1. ```cd vagrant/mysql```
2. ```docker build -t mysql .```
3. ```docker run --rm -d --name mysql mysql```
4. ```docker exec -it mysql bash```
5. ```ps -ef```
6. ```netstat -tulpen```
7. ```exit```


## Diagramm

![diagram](/doku/svg/netzplan-wordpress.svg "diagram")