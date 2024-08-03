# OpenLANE Instalation
For ease of installation, OpenLane uses Docker images.

## Please Follow This link to Install Docker 
https://docs.docker.com/engine/install/

## Please Follow This Link to Install HomeBrew
https://brew.sh/
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

These images include OpenLane’s applications, binaries as well as all the required dependencies.

All of the flow tools are encapsulated inside the container image.

## Installation of required Packages

```
brew install python make
brew install --cask docker
```

If the brew and dependencies are already installed, make sure they are upto date
```
brew update
brew upgrade python make
brew upgrade --cask docker
```

Now Restart your computer
and Open the docker app from all apps


## Checking the docker Installation
```
docker run hello-world
```


## Checking Instalation Requirements
```
git --version
docker --version
python3 --version
python3 -m pip --version
make --version
python3 -m venv -h
```

see that they are the latest version

## Download and Install OpenLANE

Download OpenLane from GitHub:
```
git clone --depth 1 https://github.com/The-OpenROAD-Project/OpenLane.git
cd OpenLane/
make
make test
```

If all the Installation work succesufully then you will recieve a messages
```
basic test passed
```

After instalation Look
<img width="1334" alt="Screenshot 2024-08-03 at 9 01 58 PM" src="https://github.com/user-attachments/assets/1fc42f6c-01c3-4802-801a-d9797f094999">

After that run the Following Command
```
make mount
```
<img width="1347" alt="Screenshot 2024-08-03 at 9 00 58 PM" src="https://github.com/user-attachments/assets/56d9ef04-2b43-476e-bb08-956a420368e3">
