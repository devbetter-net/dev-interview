# Install wsl 
https://learn.microsoft.com/en-us/windows/wsl/install

# Install Ubuntu
wsl --install Ubuntu

# Install Brew
Goto https://brew.sh/
and run command: 
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
## Note: In Linux, we need to run "Next Step"

# Install Nodejs

goto https://nodejs.org/en/download/package-manager 
copy bash script to run
brew install node@20

# Use Visual Code in WSL 
https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode

# Install Git
Debian/Ubuntu
For the latest stable version for your release of Debian/Ubuntu

apt-get install git

## Install Docker Engine on Ubuntu

0. **Run the following command to uninstall all conflicting packages:**

    ```sh
    for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

    ```

1. **Set up Docker's apt repository.**
    ```sh
    # Add Docker's official GPG key:
    sudo apt-get update
    sudo apt-get install ca-certificates curl
    sudo install -m 0755 -d /etc/apt/keyrings
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    sudo chmod a+r /etc/apt/keyrings/docker.asc

    # Add the repository to Apt sources:
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    ```

2. **Install the Docker packages.:**
    ```sh
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
    ```

3. **Verify that the Docker Engine installation is successful by running the hello-world image.**
    ```sh
    sudo docker run hello-world
    ```

4. **Update the apt package index, and install the latest version of Docker Engine, containerd, and Docker Compose:**
    ```sh
    sudo apt-get update
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
    ```

note: need to start and enable docker if need to auto start with wsl

    ```sh
    sudo systemctl start docker
    sudo systemctl enable docker
    ```
refer: https://docs.docker.com/engine/install/ubuntu/

## **Install dotnet on Ubuntu:**
### **Instal SDK**

    
    sudo apt-get update && \
    sudo apt-get install -y dotnet-sdk-8.0
    
### **Dependencies**

    
    sudo apt install zlib1g
    