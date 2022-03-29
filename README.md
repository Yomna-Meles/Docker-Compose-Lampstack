# Docker-Compose-Lampstack
Building Lampstack using Docker Compose

1- create a machine and install docker on it

I already had an Ubuntu machine that is "Docker" ready. You could easily follow up this link to easily install Docker on you machine
https://docs.docker.com/engine/install/ubuntu/


2- Create a directory and add php file

3-Docker Compose:
In this project I will use docker compose which is a tool for defining and running multi-container Docker applications. With 
Compose, you use a YAML file to configure your application’s services. Then, with a 
single command, you create and start all the services from your configuration.

To install docker compose:

# sudo apt install docker-compose 

Errors Faced Here: when trying to install Docker Compose this error showed: "Waiting for cache lock: Could not get lock /var/lib/dpkg/lock-frontend. It is held by process 3732"

This error means that apt is now in use by other processes so let's check:
# ps aux | grep -i apt

Either kill these processes or if you see the process "apt.systemd.daily update" just wait few minutes and try again. This is the daily auto update process you could know more about this error through this link 
https://itsfoss.com/could-not-get-lock-error/

3-create docker compose yaml file:

# vi docker-compose.yml 
   3.1 Define the version
      You must set a version that suits the docker compose version and that of Docker.

   3.2 List Services that we will use 
       So basically here we will need: db and apache. 
       
   3.3 Mention Images
       I have used ready-made images for my services found on docker hub. (you could use any favorable version just edit the attribute)




4- Run docker compose file

#docker-compose up


5- Let's check is this works!

  Go to your VM browser and head to "localhost" 

Errors FAced Here: if you got a 403 response the file is either not in the correct path (check yaml file) or you'll need to change the file's mode to allow it to be executable 
# chmod +x filename 

Voila!
 Now have two containers one running our DB service and the other running the apache service. 

See you in the next project where I'll be creating my own images.
