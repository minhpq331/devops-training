# Module 8: Setup SSL

In this module, you will learn how to secure your website with HTTPS/SSL by using a free certificate from Let’s Encrypt. SSL ensures that all data transmitted between your server and users is encrypted, so any man-in-the-middle like your ISP, wifi admin,... can not read your request's data, which protects sensitive information like username, password, credit card number, etc.

## Requirements

Our goal in this module is to install Certbot, obtain an SSL certificate for your domain using the ACME HTTP challenge, and update the Nginx configuration to enforce HTTPS both frontend and backend endpoints.

## Instructions

1. Understand about SSL, HTTPS and how it can protect your data on the wire. Learn more about trusted SSL certificates, self-signed certificates, how they are different and why you need an certificate issuer. What is the ACME protocol and how many ways to verify that you owned the domain name?
2. Install Certbot (a tool to manage your free SSL certificate using Let’s Encrypt) on your server. Choose the right OS and software you want to integrate your certificate with. In this case is `nginx`
3. Using Certbot to obtain an SSL certificate for your domain using the ACME HTTP challenge. Pay attention to the command to obtain the certificate.
4. Once the certificate is obtained, configure Nginx to enforce HTTPS. There're two things that need to be done:
    - Configure Nginx to listen on port 443 and use the issued certificate above
    - Setup Nginx to redirect users from HTTP to HTTPS.
5. Setup Certbot to automatically renew certificates when they nearly expire.
6. Test your application using HTTPS and make sure the frontend can serve correctly js, css and can connect to the backend on the browser.
7. (Bonus) For multiple domains like `https://example.com` for frontend and `https://api.example.com` for backend, you can try to setup a multiple-domains certificate or wildcard certificate (`example.com` + `*.example.com`) so one certificate can be used for multiple domains without having to issue a separate certificate for each domain. You can use ACME DNS challenge instead of HTTP challange to verify the wildcard certificate

## Important notes

- SSL certificates from Let’s Encrypt expire every 90 days. Certbot can set up automatic renewal, but regular checks or a tool like uptime robot, kuma, etc. can help prevent any certificate expiration issues. You need to test the ability to reload Nginx after updating the SSL certificate. 
- Make sure after configuring Nginx to enforce HTTPS, your nginx can still serve ACME requests using HTTP so Certbot can automatically renew your certificates