# AWS EC2 Static Website Deployment

## Project Overview

This project demonstrates how I deployed a static website on **Amazon EC2** using **Amazon Linux 2023** and the **Apache HTTP Server**.

The goal was to understand the fundamentals of cloud computing, virtual servers, web server configuration, and network security using AWS.

## Technologies Used

- **Amazon EC2** — Cloud-based virtual server
- **Amazon Linux 2023** — Server operating system
- **Apache HTTP Server** — Web server
- **HTML5** — Webpage structure
- **CSS3** — Webpage styling
- **EC2 Security Groups** — Network access control

## Architecture

```text
          Website Visitor
                 |
                 | HTTP Request (Port 80)
                 v
        EC2 Security Group
                 |
                 v
       Amazon EC2 Instance
        Amazon Linux 2023
                 |
                 v
       Apache HTTP Server
                 |
                 v
          index.html
                 |
                 v
          Website Displayed
```

## Implementation Steps

### 1. Launch an EC2 Instance
- Launched an EC2 instance using Amazon Linux 2023.
- Selected the `t3.micro` instance type.
- Verified that the instance was running and passed its status checks.

### 2. Configure Network Access
Configured the EC2 security group to allow HTTP traffic on port 80.

SSH access should be restricted to my own IP address rather than opened to everyone.

### 3. Install Apache

Installed Apache using the following command:

```bash
sudo dnf install httpd -y
```

### 4. Start the Web Server

Started Apache and configured it to start automatically after a reboot:

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

### 5. Create the Website

Created a custom HTML webpage and styled it using CSS.

The webpage displays information about the AWS environment and the technologies used in the project.

### 6. Verify the Deployment

Checked the Apache service:

```bash
sudo systemctl status httpd
```

Tested the HTTP response locally:

```bash
curl -I http://localhost
```

The server returned `HTTP/1.1 200 OK`, confirming that it successfully responded to the HTTP request.

## Screenshots

### 1. Live Website
![Live Website](screenshots/01-live-website.png)

### 2. EC2 Instance
![EC2 Instance Running](screenshots/02-ec2-instance-running.png)

### 3. Apache Service Status
![Apache Status](screenshots/03-apache-status.png)

### 4. HTTP Response
![HTTP Response](screenshots/04-http-response.png)

## Key Learnings

Through this project, I learned how to:

- Launch and manage an Amazon EC2 instance.
- Work with Amazon Linux 2023.
- Install and configure Apache HTTP Server.
- Host a static website on a cloud server.
- Configure security group rules for HTTP access.
- Verify a web server using Linux commands.
- Troubleshoot basic deployment issues.

## Future Improvements

- Configure a custom domain using Amazon Route 53.
- Enable HTTPS using an appropriate TLS setup.
- Automate deployment using a script.
- Explore hosting static websites using Amazon S3.

## Project Status

**Completed:** Static website successfully deployed on Amazon EC2.

**Author:** Cloud Computing Learner
