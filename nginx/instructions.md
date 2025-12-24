### Install & Configure Nginx on a AWS EC2 server

Step 1 : **Run a docker container to run Ubuntu OS** 

` docker run -itd --name ubuntu -v myubuntu_vol:/path/in/container ubuntu:22.04` \

Step 2 : **SSH into your container** 

`docker exec -it ubuntu bash` \

Step 3 : **Install Ansible on your docker Ubuntu container** \

`apt update && apt install ansible -y` \

Step 4 : **Test the connection to your servers from inventory.ini** \

`ansible all -i inventory.ini -m ping` \
```
#inventory.ini
[servers]
public-IP_address
```

Step 5 : **Run the nginx.yaml** \

`ansible-playbook -i inventory.ini nginx.yaml` \