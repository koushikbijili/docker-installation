# Docker Installation Script for Ubuntu Server

This repository contains a **bash script** that automates the installation of Docker on Ubuntu servers.

## 🧩 What this script does

- Updates existing packages on your system to the latest versions.  
- Removes any old versions of Docker (if present).  
- Installs prerequisite packages (`ca-certificates`, `curl`, `gnupg`, `lsb-release`).  
- Adds Docker’s official GPG key and sets up the Docker repository.  
- Installs Docker Engine, CLI, `containerd`, `docker-buildx-plugin` and `docker-compose-plugin`.  
- Enables and starts the Docker service.  
- Adds the current user to the `docker` group so you can run `docker` commands without `sudo`.

## 🧰 Usage

Run the following command on your Ubuntu server:

```bash
curl -fsSL https://raw.githubusercontent.com/koushikbijili/docker-installation/refs/heads/main/installation-file | sudo bash
````

After the script finishes:

* **Logout & login** again (or run `newgrp docker`) so that your user session picks up the `docker` group changes.
* Verify the installation by running:

  ```bash
  docker --version
  ```

## ✅ Pre-requisites

* An Ubuntu server (tested on Ubuntu 20.04 / 22.04).
* A user with `sudo` privileges.
* Internet access to download the packages and repository information.

## 🔧 Post-installation Tips

* You may pull and run a test Docker image:

  ```bash
  docker run hello-world
  ```

* If you want to check the Docker daemon status:

  ```bash
  sudo systemctl status docker
  ```

* To manage Docker as a non-`sudo` user, ensure you re-login or run:

  ```bash
  newgrp docker
  ```

```
