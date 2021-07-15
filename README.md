# Gitlab_DockerCompose
Install Gitlab using Docker compose file 

# Create a new directory
mkdir gitlab
cd gitlab

#Create docker-compose.yml file
##vim editor
sudo vim docker-compose.yml
or
##nano editor
sudo nano docker-compose.yml
add the content from docker-compose.yml file from the git

##If vim editor
Press Esc + :wq to save and exit

##if nano editor
Press Ctrl+ X , then Enter

## Execute the docker compose file
docker-compose up -d

##Validate Container have started and healthy
docker ps -a

## Access
http://localhost:8080/

##If DNS used
Change the line 22 in docker-compose file to Domain
then Access using 
https://<domain>:8080/

 **NOTE**
  If password Reset page doesnt appear
  
  Follow the steps
  ## Login to the gitlab container
  docker ps -a
  docker exec -it <containerID> bash
  
  gitlab-rails console -e production
  u = User.where(id:1).first
  u.password = ‘<enter_your_password_here>’
  u.password_confirmation = ‘<enter_your_password_here>’
  u.save!
  exit
  exit
  
  ## Aceess 
  http://localhost:8080
  or 
  https://<domain>:8080

  
  
