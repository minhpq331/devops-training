# Module 5: Deploy frontend

In this module, you will deploy the frontend application to your server. The most common frontend is a React application. You should know what architecture your frontend application is using and what type of deployment you need to implement before starting this module. Here are some basic requirements and instructions to complete the module with a React frontend.

## Requirements

Our goal in this module is to deploy a React frontend application to the server. The frontend application should be able to connect to the backend server and serve the frontend pages.

## Instructions

1. Install correct Node.js version on the server. Because you have already deployed the backend application with Node.js, you only need to make sure you are using the correct Node.js version for the frontend application. 
2. Clone the frontend application code to your server using Git. Please avoid using any personal tokens/keys to clone the repository. Learn how to use Deploy/Project keys with read-only access to the repository.
3. Install dependencies, configure environment and build your frontend application.
4. Serve the frontend application using a web server. In case of static distribution, you can use Nginx to serve the static files. If you have a server-side rendering application, you can use Node.js to serve the application. Avoid port conflicts with the backend application.
5. Start your application with a process manager like `pm2` or `forever`. Make sure the application is restarted automatically if it crashes or after server reboots.
6. Expose the frontend application to the internet. You need to listen on a public interface and allow traffic to your port through the firewall.
7. Access your application using <server-ip>:<port> in the browser. Make sure you can access the frontend application and it can connect to the backend application to fetch data.

## Important notes

- The most important part of this module is make sure your frontend application can connect to the backend application in both server-side and client-side. There're some common issues like setting the correct backend address, firewall rule, CORS policy that you should be aware of.