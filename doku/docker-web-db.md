# Docker Wordpress mit DB

## Apache Container
1. cd /vagrant/web
2. ```sudo apt install apache 2```
3. ```docker run --rm -d -p 8080:80 -v `pwd`/web:/var/www/html --name apache apache```
4. Testen mit ```curl http://localhost:8080```
   
## MySQL Container

