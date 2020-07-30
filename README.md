# kafkar
ELM327 OBD2 to Kafka Topic(s)

Hardware Used: Raspberry PI 4 4GB, ELM 327 Bluetooth Module

Step 1: Have Raspbery Pi OS (Raspbian) running on your RPi4 and Update
```
sudo apt update
sudo apt upgrade
```

Step 2: Install Docker
```
curl -sSL https://get.docker.com | sh

```

Step 3: Install Portainer
```
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

Step 4: Run Docker Compose 
To-do: Upload docker-compose.yml file into repo

Step 5: Pair with ELM327 using Bluetooth
```
sudo bluetoothctl 
> agent on
> default-agent 
```
Now, ensure that the ELM327 is powered on and ready to pair. The following commands will pair and connect the ELM327 to your RPi4:
```
> scan on
> pair [device Bluetooth address]
> connect [device Bluetooth address]
```
