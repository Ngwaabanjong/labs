# INSTALL Docker WITH SCRIPT on all Linux Engines:
``````
sudo wget https://raw.githubusercontent.com/lerndevops/labs/master/scripts/installDocker.sh -P /tmp
sudo chmod 755 /tmp/installDocker.sh
sudo bash /tmp/installDocker.sh
sudo systemctl restart docker
``````
## Check installation
``````
docker --version
docker-compose --version
``````

## Install docker compose
``````
sudo apt install docker-compose
``````
