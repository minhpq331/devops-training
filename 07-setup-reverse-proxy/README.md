# Module 7: Setup a reverse proxy

In this module, you will learn how to set up a reverse proxy using Nginx. A reverse proxy allows you to run multiple services (like backend and frontend applications) on the same domain without specifying the port, routing requests to the appropriate service based on the URL path or subdomain.

## Requirements

Our goal in this module is to configure Nginx as a reverse proxy on our server. This will enable requests to be forwarded to your backend and frontend applications seamlessly on the same domain (or different domain with the same port).

## Instructions

1. Install Nginx as the reverse proxy on your server. Read more about how to install Nginx on Ubuntu. You can use the OS package manager to install Nginx.
2. Locate the nginx configuration folder, configuration files and how that file is constructed. Pay attention to some folders like `conf.d`, `site-available`, `site-enabled`,... to understand how to configure nginx properly. Read more about nginx configuration best practices and where to put your configuration.
3. Disable the default vhost configuration and restrict nginx to serve only the domain you want so if anyone access your server's IP directly or through malicious domains at port 80, they will receive an access denied error.
4. Configure Nginx vhost by adding a server block configuration file to `site-available` folder. Listen on port 80 and use the same domain for both frontend and backend:
    - Use location / to serve the frontend application
    - Use location /api/ to serve the backend application and strip the prefix /api/ when the request reaches your backend. For ex: Your backend api will be http://localhost:3000/auth/signup but the request from client will be http://yourdomain.com/api/auth/signup
5. Create a symlink to the vhost file in `site-enabled` folder to include it in nginx configuration. Check the configuration syntax carefully using nginx command `nginx -t`. After that you can reload nginx to use the new configuration.
6. Test your application using your domain instead of the server's IP and port. You should test both the frontend and backend and make sure the frontend can serve correctly js, css and can connect to the backend on the browser.
7. (Bonus after you complete step 2) Configure Nginx to listen on port 80 and use 2 different domains for frontend and backend:
    - Use domain `yourdomain.com` to serve the frontend application
    - Use domain `api.yourdomain.com` to serve the backend application
8. Test again to make sure your application is working properly.    

## Important notes

- Despite the fact that this module is quite easy to complete, it is still very challenging to get it right. Some of the configuration is a bit tricky like:
    - Configure the correct prefix path at step 4. Pay attention to how the location block is configured and the difference between each type of location path and proxy_pass location.
    - Configure the CORS at step 7. Yeah, you will face the CORS problem at this step if you test your application properly. Don't just follow the instructions from the internet which tells you to bypass CORS or allow `*`. We won't do that. Try to understand CORS completely and set your CORS configuration carefully to protect your backend from being called from a malicious domain other than your frontend.
- Nginx will be a very important part of your DevOps's life - no kidding, and you should spend large amount of time to understand how it works and how to configure it properly, including:
    - Location configuration and how nginx matches requests against those locations
    - Nginx proxy module configurations and timeout configurations
    - Some best practices like hardening security for your website, protect hidden files, preventing XSS, clickjacking, etc.

## Useful Resources

- [How to install Nginx on Ubuntu 22.04](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-22-04): The basic guide on how to install Nginx everyone should know
- [Understanding Nginx Server and Location Block Selection Algorithms](https://www.digitalocean.com/community/tutorials/understanding-nginx-server-and-location-block-selection-algorithms): Explaination about how Nginx's matching engine works.
- [Nginx reverse proxy security and performance best practices](https://maxtsh.medium.com/nginx-reverse-proxy-security-and-performance-best-practices-e47f599c8fed): Some basic and easy-to-use configurations for securing your Nginx
- [Nginx Admins Handbook](https://github.com/trimstray/nginx-admins-handbook): The dictionary to deep dive into Nginx's administration