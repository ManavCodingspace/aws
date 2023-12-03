# ***OPENSTACK DEPLOYING***

How to Install OpenStack on Ubuntu with DevStack

What is Openstack
OpenStack is a free, open standard cloud computing platform. It is mostly deployed as infrastructure-as-a-service in public and private clouds where virtual servers and other resources are available to users.

    sudo apt update
    
    sudo apt upgrade
    
    sudo reboot

    sudo useradd -s /bin/bash -d /opt/stack -m stack
    sudo chmod +x /opt/stack

    echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack

    su - stack

    sudo apt install git -y
     
     git clone https://git.openstack.org/openstack-dev/devstack
    
    cd devstack
    
    vim local.conf

    [[local|localrc]]

# Password for KeyStone, Database, RabbitMQ and Service

    ADMIN_PASSWORD=StrongAdminSecret
    DATABASE_PASSWORD=$ADMIN_PASSWORD
    RABBIT_PASSWORD=$ADMIN_PASSWORD
    SERVICE_PASSWORD=$ADMIN_PASSWORD

# Host IP - get your Server/VM IP address from ip addr command
    HOST_IP=10.208.0.10

    ./stack.sh
    
    [./stack.sh](https://server-ip/dashboard)https://server-ip/dashboard

    
