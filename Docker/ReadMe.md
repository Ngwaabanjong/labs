# INSTALL Docker WITH SCRIPT on all Linux Engines:
Sudo wget https://github.com/Ngwaabanjong/labs/blob/main/Docker/installDocker.sh -P /opt
sudo chmod 755 /opt/installDocker.sh
sudo bash /opt/installDocker.sh

sudo apt-get install docker-ce docker-ce-cli containerd.io
sudo apt install docker.io
sudo apt install docker-compose

Docker --version
Docker-compose --version