# Module 2: Setup a server

In this module, you will learn how to setup a server to host your applications. Below are basic requirements and instructions to complete the module. But you can do more than that. Feel free to explore and try new things. You can add your notes, commands, and configurations to this module's folder. 

## Requirements

Our goal in this module is a ready-to-use server with basic security configurations.

## Instructions

1. Create a new server on any cloud provider, it should run Ubuntu (LTS version preferred). A minimum instance type will do. There are several cloud providers provide free tier for 1 year, you can use them.
2. Login to the server public IP using SSH and the credentials provided by the cloud provider.
3. Create a new user with sudo privileges. You should not use the `root` user to manage your server. After that, disable the `root` user login.
4. Setup SSH key-based authentication for the new user. You should not use password-based authentication. After that, disable the password-based authentication completely.
5. Change the default SSH port to a custom port. You can choose any port number between 1024 and 65535.
6. Update the server packages and install basic tools like `vim`, `curl`, `wget`, `htop`, `net-tools`, etc.
7. Setup a basic firewall using `ufw` or `iptables`. Allow only SSH (or your custom port), HTTP, and HTTPS ports. You can use cloud provider's firewall as well, make sure you use `telnet` command to check if the firewall is working properly.