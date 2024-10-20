# docker-set-up


This guide will walk you through setting up Docker and Docker Compose on your Ubuntu system. **Note:** Visual Studio Code (VS Code) should already be installed.

## Step 1: Install Docker

1. **Update the package list:**
   
                   sudo apt-get update


3. **Install prerequisite packages:**
 
                sudo apt-get install \
                ca-certificates \
                curl \
                gnupg \
                lsb-release


4. **Add Docker's official GPG key:**

   sudo mkdir -p /etc/apt/keyrings
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   

5. **Set up the stable repository:**
 
   echo \
     "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 

6. **Install Docker Engine:**

   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
  

7. **Verify that Docker is installed correctly by running the hello-world image:**
 
   sudo docker run hello-world
  

## Step 2: Install Docker Compose

1. **Download the latest version of Docker Compose:**

   sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep -oP '(?<="tag_name": ")[^"]*')/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose


2. **Apply executable permissions to the binary:**

   sudo chmod +x /usr/local/bin/docker-compose
  

3. **Verify installation:**

   docker-compose --version
  
