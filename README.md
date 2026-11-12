# react-nginx-ubuntu-deployment
# Deploying a React Application on AWS EC2 Using Nginx 

## Project Overview

As part of Week 3 of the DevOps Micro Internship (DMI), I deployed a React application on an Ubuntu server hosted on AWS EC2.

The goal was to get hands-on experience with Linux server administration, AWS infrastructure and using Nginx to serve a web application.

## Tools & Technologies

- **AWS EC2** – Hosting the Ubuntu server.
- **Ubuntu Linux** – Server operating system.
- **Nginx** – Serving the React application.
- **React** – Frontend application.
- **SSH** – Connecting to the remote server.
- **Git & GitHub** – Version control and project documentation.

## Deployment Process

1. **Created an EC2 instance:** Launched an Ubuntu server on AWS and configured the necessary security group rules.

2. **Connected to the server:** Used SSH to access and manage the Ubuntu instance.

3. **Installed Nginx:** Installed and started Nginx to serve the application.

4. **Built the React application:** Ran the necessary npm commands to generate production-ready files.

5. **Deployed the files:** Copied the production files into `/var/www/html/`, Nginx's default web directory.

6. **Configured Nginx:** Set up the server configuration to serve the application and support React client-side routing.

7. **Tested the deployment:** Accessed the EC2 public IP address through a browser to verify the application.

## Nginx Configuration

The following configuration supports React client-side routing:

```nginx
server {
    listen 80;
    server_name _;

    root /var/www/html;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

## Challenges Faced 

During deployment, I encountered an error when copying the production files:

```bash
cp: cannot stat 'build/*': No such file or directory
```

The expected `build` directory wasn't available in my working location. I had to check the project files and identify the correct build output before continuing.

This taught me to verify file locations and build directories before running deployment commands.

## Screenshots
![Screenshot 1](./Screenshots/Server.png)
![Screenshot 3](./Screenshots/React_Deployment.png)
![Screenshot 8](./Screenshots/React_nginx_config.png)
![Screenshot 9](./Screenshots/React_Curl.png)
## What I Learned

- Deploying applications on AWS EC2.
- Connecting to and managing Ubuntu servers using SSH.
- Installing and configuring Nginx.
- Preparing React applications for production.
- Understanding how Nginx serves web applications.
- Troubleshooting deployment errors.

## Conclusion

This project gave me practical experience deploying a frontend application on a cloud server. It also helped me understand how AWS EC2, Linux and Nginx work together to make an application accessible over the internet.

I'm looking forward to building on this knowledge as I continue my DevOps journey.

---

