# ansible


## target preprocess
```
sudo apt-get update
sudo apt install -y openssh-server
sudo sed -i 's/#Port 22/Port 2222/' /etc/ssh/sshd_config
sudo service ssh start

hostname -I
```

## ansible client
```
docker compose up -d
```

## post process
```
sudo service ssh stop
sudo sed -i 's/Port 2222/#Port 22/' /etc/ssh/sshd_config
sudo apt purge openssh-server
```