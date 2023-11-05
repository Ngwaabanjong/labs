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
## Configure docker user
This helps to avoid permission issues with the docker daemon

**bash:**
A safe approach in running docker is to add user to group 
```
sudo groupadd docker
sudo usermod -aG docker $USER
# logout of instance and login again
```

**Give user ownership to  avoid sudo docker:

**bash:**
```
sudo chown "$USER":"$USER" /home/"$USER"/.docker -R
sudo chmod g+rwx "$HOME/.docker" -R
````
**Check to make sure the daemond is owned by the group**
```
ls -l /var/run/docker.sock
#result: srw-rw----. 1 root docker 0 Nov  5 04:52 /var/run/docker.sock
```
**Check without _sudo_, by running a _hello world_ container:**  
```docker run hello-world```
