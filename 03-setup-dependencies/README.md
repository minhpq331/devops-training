# Module 3: Setup dependencies

In this module, you will learn how to setup dependencies for your applications like databases, caches, message brokers, etc. It upto your application requirements. Here are some basic requirements and instructions to complete the module.

## Requirements

Our goal in this module is to setup a database server with basic configurations and basic security.

## Instructions

1. Choose a database server to install. You can choose any database server like MySQL, PostgreSQL, MongoDB, etc. based on your application requirements.
2. Install the database server on your server. Read more about how to install that database on Ubuntu. You can use the package manager to install the database server.
3. Locate **the configuration folder** and **the data folder** of the database server. You should know where the configuration files are located and where the data files are stored. If your db's disk is full, you should be able to move the data folder to another disk.
4. Implement some basic configuration tweaks. Read more about the best practices for configuring that database server and apply them. It can be increasing the buffer size, changing the default port or address, increasing the maximum open files limit, etc.
5. Setup a basic security configuration. Read more about securing that database server and apply them. It can be setting up a password for the root user, disabling remote access, change listening address, removing guest db, etc.
6. Create a new database and a new user. You should not use the root user to manage your database. After that, grant the necessary permissions to the new user.
7. Configure the firewall to block the database server port from public access. In order to connect to the database server port, you should use SSH tunneling or VPN.

## Important notes

- Many database servers have their default configurations insecure. MySQL or MongoDB are examples of this. You should always read the security best practices to change the default configurations of those databases.
- It's good to start listening your database server on LAN address (localhost is too restrictive) because it's a common practice to have other applications on the same network to connect to the database server.
- NEVER expose your database port to the public internet unless there's a strong reason to do so. Always use SSH tunneling or VPN to connect to the database server from your local machine.

## Useful Resources

- [How to install MongoDB on Ubuntu 22.04](https://www.cherryservers.com/blog/install-mongodb-ubuntu-22-04): A basic installation of MongoDB and how to enable authentication
- [How to install MySQL on Ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04): A basic installation of MySQL and how to enable authentication, authorization
- [Optimizing Your Linux Environment for MongoDB](https://severalnines.com/blog/optimizing-your-linux-environment-mongodb/): Some basic OS tweaks for MongoDB
- [OS Optimization for MySQL Performance](https://www.linkedin.com/pulse/os-optimization-mysql-performance-prabhat-kumar-q9osc/): Some basic OS tweaks for MySQL performance (to get you familiar with this habit when installing anything)
- [Database Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Database_Security_Cheat_Sheet.html): Some best practices for securing your database. Always read more about securing your database and apply them at the first place.