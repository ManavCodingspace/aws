# ***AWS AND DOCKER INSTALLATION***
AWS Management Console:

Web-based interface for managing AWS services
AWS Global Infrastructure:

AWS global data center network
Availability Zones:

AWS data center clusters
Amazon EC2 Instance Types:

EC2 virtual machine configurations
Storage and Database:

Amazon S3: Object storage
Amazon RDS: Managed databases
Amazon DynamoDB: Managed NoSQL
Docker Installation
Quick Install
curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash
installing packages:

sudo apt update
sudo apt install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release \
    jq
Add Docker’s official GPG key:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
setup repository:

echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
Install Docker Engine:

sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
Add your user to the docker group:

sudo usermod -aG docker $USER
Docker Compose
download the current stable release of Docker Compose:

COMPOSE_VERSION=$(curl -s "https://api.github.com/repos/docker/compose/tags" | jq -r '.[0].name')
sudo curl -L "https://github.com/docker/compose/releases/download/${COMPOSE_VERSION}/docker-compose-$(uname -s)-$(uname -m)" \
  -o /usr/local/bin/docker-compose
Get executable permissions to the binary:

sudo chmod +x /usr/local/bin/docker-compose
Pull Docker Images
docker pull hello-world
docker pull nginx
docker pull ubuntu/apache2
Listed Images
docker images
Port Forwarding nginx
docker run --name mynginxl -p 80:80 -d nginx
Killing nginx to run Apache2
docker kill mynginxl
Port Forwaring Apache2
docker run --name myapache -p 80:80 -d ubuntu/apache2
