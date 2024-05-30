# ansible


## preconditions
```
sudo apt-get update
sudo apt install openssh-server

export BEFORE_HOSTNAME=$(hostname)
export AFTER_HOSTNAME=docker

sudo hostnamectl set-hostname $AFTER_HOSTNAME
sudo sed -i "s/$BEFORE_HOSTNAME/$AFTER_HOSTNAME/g" /etc/hosts

sudo sed -i 's/#Port 22/Port 2222/' /etc/ssh/sshd_config
sudo service ssh start
```

## client
```
sudo apt-get update
sudo apt-get install ansible

sudo apt-get update
sudo apt install sshpass

ansible-playbook -i inventory playbook.yaml
```