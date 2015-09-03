# docker-compose-demo
A short demo on how to use docker-compose to create a Web Service connected to a load balancer and a Redis Database. 

# Install
The instructions assume that you have already installed [Docker](https://docs.docker.com/installation/) and [Docker Compose](https://docs.docker.com/compose/install/). 

In order to get started be sure to clone this project onto your Docker Host. Create a directory on your host. Please note that the demo webservices will inherit the name from the directory you create. If you create a folder named test. Then the services will all be named test-web, test-redis, test-lb. Also, when you scale your services it will then tack on a number to the end of the service you scale. 

    git clone https://github.com/vegasbrianc/docker-compose-demo.git .

# How to get up and running
Once you've cloned the project to your host we can now start our demo project. Easy! Navigate to the directory in which you cloned the project. Run the following commands from this directory 
    docker-compose up -d

The  docker-compose command will pull the images from Docker Hub and then link them together based on the information inside the docker-compose.yml file. This will create ports, links between containers, and configure applications as requrired. After the command completes we can now view the status of our stack

    docker-compose ps

Verify our service is running by either curlng the IP from the command line or view the IP from a web browser

###Curling from the command line
    curl 0.0.0.0
    
    Hello World!
    I have been seen 1 times.
    My Host name is 29c69c89417c

# Scaling
Now comes the fun part of compose which is scaling. Let's scale our webservice from 1 instance to 5 instances.

   docker-compose scale web=5
This will now scale our web service container. Now run our curl command again on our web services

