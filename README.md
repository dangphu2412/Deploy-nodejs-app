# How to deploy

## Create a new Vps on digital ocean
- https://www.digitalocean.com/community/questions/how-to-setup-vps-on-digitalocean
- We need to create a new droplet
- Create new user and not using root
```sh
add user fus

usermod -aG sudo fus
```
- Setup firewall in ubuntu to enable access via ssh
```sh
ufw app list
ufw allow OpenSSH
ufw enable
ufw status
```

- Setup ssh access by the common user (fus)
```sh
ls -lah ~/
ls -lah ~/.ssh/ #This is the ssh folder of root user and now we need to copy it into common user

ls -lah /home/fus
mkdir -lah /home/fus/.ssh
cp ~/.ssh/authorized_keys /home/fus/.ssh

chown -R fus: /home/fus/.ssh
ls -lah /home/fus/.ssh # Can be access by user fus
```