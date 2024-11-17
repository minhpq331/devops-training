# Module 4: Deploy backend

In this module, you will learn how to deploy a backend application to your server. Based on your choosed backend technology, you will have different steps to deploy the application. Here are some basic requirements and instructions to complete the module with a nodejs backend.

## Requirements

Our goal in this module is to deploy a nodejs backend application to the server. The backend application should be able to connect to a database server and serve the API requests.

## Instructions

1. Install Node.js on your server. You can use the package manager to install Node.js. Make sure you install the LTS version of Node.js. In case of specific version requirements, you can use `nvm` to manage multiple Node.js versions. Install by following the instructions on the [official Node.js website](https://nodejs.org/). Package manager installation is recommended for simplicity.
2. Copy the backend application code to the server. This module expects you to use a simple tool like `scp` or `rsync` to copy the code to the server. You can also use a version control system like Git to clone the code to the server. But I think using `scp` or `rsync` is enough for this module and provides you with the basic knowledge of how to copy files to the server. This is a very useful technique in real-world scenarios.
3. Prepare the `.env` file for the backend application. The `.env` file should contain the environment variables required by the backend application. You can use the `.env.example` file to create the `.env` file on server. Make sure you don't commit the `.env` file to the version control system.
4. Install the dependencies of the backend application. You can use the `npm install` command to install the dependencies.
5. Start the backend application. You can use the `npm start` command or `node index.js` directly to start the backend application. Make sure the application is running and you can access the API endpoints with `curl`.
6. Use a process manager to keep the backend application running. You can use `pm2` or `forever` to keep the backend application running in the background. `pm2` is recommended for your application. Make sure the application is restarted automatically if it crashes or after server reboots.

## Important notes

- When you copy the code to the server, make sure you don't copy the `.git` folder, `node_modules` folder or the `.env` file. You should only copy the necessary files to run the application.
- Install correct Node.js version on the server. If your backend and frontend applications have different Node.js versions, you should use `nvm` and learn how to use `.nvmrc` file to specify the Node.js version for the application.
- Mind the application host and port. You should learn about different network interfaces and how to bind the application to a specific interface or all interfaces. You should also learn how to change the application port if it's already in use by another application. This is important for running multiple applications on the same server and avoid port conflicts. This affects your server's security as well. For example, if you have a reverse proxy in front of your application, you should bind the application to `localhost` and a specific port, and let the reverse proxy handle the public access.
- When using a process manager, you should define all your params in a declarative way. Try not to use params in the command line because it is not reproducible.

## Useful Resources

- [Deploying Node.js applications with PM2](https://developer.mozilla.org/en-US/blog/deploying-node-js-applications-with-pm2-on-vultr/): Some basic guide to install nodejs application with pm2 on VPS
