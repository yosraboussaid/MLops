# MLops

## Setup environment

### Local environment :

Recommended development environment: Linux

Step 1: Download and install the Anaconda distribution of Python
``
wget https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh
bash Anaconda3-2022.05-Linux-x86_64.sh
``

Step 2: Update existing packages
``
sudo apt update
``

Step 3: Install Docker and Docker Compose

Follow the instructions here: install-using-the-repository
Set up Docker's apt repository.

#### Add Docker's official GPG key:
``
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
``

#### Add the repository to Apt sources:
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

Install the Docker packages.

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
To run docker without sudo:
```
sudo groupadd docker
sudo usermod -aG docker $USER
```

Step 4: Run Docker
```
docker run hello-world
If you get docker: Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied. error, restart your VM instance, or run: sudo dockerd
```

Note: If you get It is required that your private key files are NOT accessible by others. This private key will be ignored. error, you should change permits on the downloaded file to protect your private key:

```
chmod 400 name-of-your-private-key-file.pem
```

### Use GithubCodeSpace