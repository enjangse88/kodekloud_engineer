
docker run -d --name nginx_docker nginx:alpine
docker stop docker-name
docker rm docker-name
docker run -d -v /var/www/html:/usr/local/apache2/htdocs -p 80:8080 --rm httpd:latest 

#copy from host to container
docker cp <src-path> <container>:<dest-path> 
kubectl cp <src-path> <your-pod-name>:<dest-path> 

docker cp /tmp/nautilus.txt.gpg  ubuntu_latest:/opt/
#copy from container to container
docker cp <container>:<src-path> <local-dest-path> 
kubectl cp <your-pod-name>:<src-path> <local-dest-path> 


#docker retag 
docker image tag docker-image:old-tag docker-image:new-tag

add permission user to docker group
usermod -a -G anita docker
useradd anita docker
vi /etc/group --> add di bagian docker, nama username

docker exec -it container_name bash/sh