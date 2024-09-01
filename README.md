# OpenDevin Installation Guide on WSL

This guide provides step-by-step instructions for installing and setting up OpenDevin on Windows using WSL (Windows Subsystem for Linux) with Ubuntu.

## Prerequisites

- **Python 3.11+**: Ensure you have Python 3.11 or later installed.
- **Node.js**: Install Node.js using `nvm` (Node Version Manager).
- **Docker**: Install Docker inside WSL.

## Step 1: Check Python Version

First, verify that you have Python 3.11 or later installed:

```bash
python --version
```

## Step 2: Install Node.js Using NVM
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc
nvm install node
nvm use node
```

## Step 3: Install Docker Desktop 
```
https://docs.docker.com/engine/install/
```

## Step 4: Clone and Build OpenDevin

#### Clone the OpenDevin repository:
```
git clone https://github.com/OpenDevin/OpenDevin.git
cd OpenDevin/
```

#### Build the project:
```
make build
```

#### If you encounter an error regarding poetry not being found, source your profile and verify the Poetry installation:
```
source ~/.profile && poetry --version
```

#### Install Poetry (If not Installed):
```
curl -sSL https://install.python-poetry.org | python3 -
```

#### Build Again: 
```
make build
make setup-config
```
## Step 5: Run OpenDevin
#### Create a workspace directory:
```
mkdir ./workspace
```

#### Run OpenDevin:
```
make run
```
