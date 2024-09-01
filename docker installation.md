

---

# Docker Installation Guide for Ubuntu

This guide provides step-by-step instructions for installing Docker and Docker Compose on an Ubuntu system. Follow these steps to set up Docker for containerization of your applications.

## Prerequisites

- **Ubuntu**: This guide is tailored for Ubuntu. Ensure you have `sudo` privileges on your system.
- **Internet Connection**: Required to download packages.

## Steps to Install Docker

### 1. Update Package List

Begin by updating your package list to ensure you have the latest information about available packages:

```bash
sudo apt update
```

### 2. Install Required Packages

Install the required packages to allow `apt` to use packages over HTTPS:

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

### 3. Add Docker’s Official GPG Key

Add Docker's official GPG key to your system:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

### 4. Set Up the Docker Repository

Add the Docker repository to your APT sources:

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

### 5. Update Package List Again

Update your package list to include packages from the Docker repository:

```bash
sudo apt update
```

### 6. Install Docker Engine

Install Docker Engine using the following command:

```bash
sudo apt install docker-ce
```

### 7. Verify Docker Installation

Check that Docker is installed and running by verifying its version:

```bash
docker --version
```

### 8. Manage Docker as a Non-root User (Optional)

To allow running Docker commands without `sudo`, add your user to the Docker group:

```bash
sudo usermod -aG docker $USER
```

You will need to log out and log back in for the changes to take effect, or you can use the following command to apply the group change immediately:

```bash
newgrp docker
```

### 9. Start and Enable Docker Service

Ensure Docker is started and enabled to run on boot:

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

## Steps to Install Docker Compose

### 1. Download Docker Compose

Download the latest version of Docker Compose from the Docker GitHub releases page:

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

### 2. Apply Executable Permissions

Apply executable permissions to the Docker Compose binary:

```bash
sudo chmod +x /usr/local/bin/docker-compose
```

### 3. Verify Docker Compose Installation

Check the installed version of Docker Compose to confirm that it was installed correctly:

```bash
docker-compose --version
```

## Conclusion

Docker and Docker Compose are now installed on your Ubuntu system. You can start using Docker to containerize your applications and Docker Compose to manage multi-container Docker applications.

For more information and advanced usage, visit the [Docker Documentation](https://docs.docker.com/) and [Docker Compose Documentation](https://docs.docker.com/compose/).

---

