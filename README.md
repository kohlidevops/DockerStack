# Docker Swarm Stack

Stack is a group of interrelated services that share dependencies and can be orchestrated and scale together.

A single stack is capable of defining and coordinating the functionality of an entire application.

Complex application may have multiple stacks as well.

## Demo: To deploy a stack using Docker Swarm

**Lets play with docker play ground and choose 3 manager and 2 worker nodes**

```
https://labs.play-with-docker.com
```

connect any manager node and ssh

![image](https://github.com/user-attachments/assets/6df5ffcd-1fb6-4d0e-9667-836058501b9d)

**Clone below link to work on it.**

```
https://github.com/kohlidevops/Docker_for_DevOps.git
cd docker_webapp_stack
ls -lh
```

**_To build the image_**

```
docker build --tag=webapp .
docker images
```

![image](https://github.com/user-attachments/assets/e7710c32-c9e4-4d5c-983b-9990d2eec1d0)

**_To tag and push the docker image to docker hub_**

```
docker login
docker tag webapp:latest latchudevops/web_app:1.0
docker push latchudevops/web_app:1.0
```

**_To check the image in the docker hub_**

![image](https://github.com/user-attachments/assets/dcde4ec9-b08e-4e94-9e96-57008f8c80e3)

**_To deploy the stack using docker compose_**

```
vi docker-compose.yml
//Replace your username and image name
//image:l latchudevops/web_app:1.0

docker stack deploy -c docker-compose.yml web_app
docker service ls
docker stack ls
```

![image](https://github.com/user-attachments/assets/e4318e55-1ee6-476e-9a8e-aacb43ff25da)

![image](https://github.com/user-attachments/assets/9aecf58d-67a4-4b91-9513-35dd937c8e62)

###########Have To Learn##################3

