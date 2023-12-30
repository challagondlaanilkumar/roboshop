# roboshop project with docker and docker-compose 

Reference for docker docs : https://docs.docker.com/engine/reference/commandline/docker/

Few commands very useful in realtime 

IMAGES
==========================================================
docker images 
docker images -q --> it will give the ids of the images 
docker rm $(docker images -q) --> it will delete all images 
docker rmi imageid --> it will delete single image
docker build -t <image> . --> it will build the image from dockerfile

PUSH
=========================================================== 
for i in web catalogue ;do cd $i ; docker build -t challagondlaanilkumar/$i:v1 . ; docker push challagondlaanilkumar/$i:v1 ; cd .. ; done --> it push the docker images into repo

CONTAINERS
============================================================
docker run -d image:tag  -->  it will run container using image 
docker run -d -p 80:80 image:tag --> it will help to mapping the ports
docker run -d -p 80:80 --name imagename image:tag  --> it will help to add name to container
docker ps -a --> it will list all containers
docker rm -f `docker ps -a -q` --> it will remove all running conatiners


NETWORK
=============================================================
docker network ls --> List all networks
docker network ls --filter driver=bridge --> it will help filter the docker networks
docker network prune --> it will delete all networks
docker run -d -p 80:80 --name imagename image:tag --network networkname image:tag -->it will add network to conatainer 
docker network rm my-network --> it will remove single network  



 
