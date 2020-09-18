# Steps to understand docker

Docker is divided as follows.
- Dockerfile
- Images
- Containers

The Dockerfile is a file that "builds" the images. Once the image is build, "run" it and make it a container.

## Resources

https://youtu.be/eGz9DS-aIeY this video is really cool. It shows you a quick 20 min video of the power of docker. It doesn't go through the basics but is good enough.

## Commands

```bash
docker images # all the images

docker ps # all containers running
docker ps -a # all containers ever started

docker exec -it name bash # so a container is running in the background and want to play w it

docker build . # where the docker file is located
docker build -t new_app:1 . # to specify name and tag
docker build -f /home/nestoregon/D1/Dockerfile . # from another directory

docker run name # to run the container
docker run -d name # ditached mode
docker run -it name # interactive mode
docker run --rm -it 07ff55298eff # removes the container with that image (the previous one)
docker run -d -t --name coolnameaf image_name # ditached, and tag?
docker run -d -t -p 80:80 image_name # This one is special cuz of the ports
# 172.17.0.1 copy this on your browser and you see what you're actually running locally

docker stats # a must to see all the stats

docker stop name # to stop containers that are running
docker start name # to stop containers that are running

docker search image_name # self explainatory

docker rm name # remove container
docker rmi name # remove image
docker rmi -f name # force the move even if there are containers
docker system prune # removes every container, dangling image and unused networks
docker system prune --volumes #everything + important data
docker container prune # removes only containers
```

## TL;DR

```bash
docker pull centos
docker run -d -t --name 2cool4school centos
docker exec -it 2cool4school sh
# you're in!
```

## Running containers

Containers IDs are so much larger than they seem.
``docker run options image args `` basic syntax

## Dockerfile syntax

Things to consider. You have a Dockerfile that it's basically going to build your image. It's a script where you specify stuff and it builds the image.
What do you specify? You may ask.
Well it's fairly simple.  
You declare the following

```dockerfile
FROM gcc:latest

COPY source destination

CMD bash # command that you want to execute
```

## Conclussion

You can run containers that have **THE SAME** kernel as the underlying operative system. Microservices are really important, how to segment processes in isolation. WHAT IS PIE WHOLE.
It relies on the linux utility and how it's being used everywhere.