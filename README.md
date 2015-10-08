data/  
 |-- db/{gudong,iasset}  
 |-- etc/nginx/conf.d  
 |-- site/htdocs{good,iasset}  
 `-- logs{mariadb,mongo,nginx,php}  

1. docker create --name site -v /workspace/(project dir):/data/site/htdocs/(project dir) docker.io/centos:6  
2. docker run -d --name nginx volumes-from site idc/nginx:1.8  
3. docker run -d --name php volumes-from site idc/php:5.2  
4. docker run -d --name mongo volumes-from site idc/mongo:3.04  

> 获取docker container IP： docker exec containerName hostname -I
