# My-first-project
Beginner-friendly project for deploying a professional static website using AWS EC2, Docker, and Nginx on Linux. Learn how to launch a cloud server, install Docker, build a Docker image, and host a public website using the AWS Free Tier. Ideal for learning cloud deployment, containerization, and web hosting basics.

AWS EC2 + Docker Simple Website Deployment

This project demonstrates how to deploy a simple professional web page using AWS Free Tier, Docker, and Linux. It uses an AWS EC2 instance as the server, Docker for containerization, and Nginx to serve a static website.

Features
Launch a free AWS EC2 server
Install and configure Docker on Linux
Create a responsive professional web page
Deploy the website inside a Docker container
Access the website using a public IP address
Technologies Used
AWS EC2
Ubuntu / Amazon Linux
Docker
Nginx
HTML & CSS
Project Workflow
Create an AWS Free Tier account
Launch an EC2 instance
Connect to the server using SSH
Install and configure Docker
Create a simple HTML webpage
Build a Docker image with Nginx
Run the Docker container
Access the website through the browser
Result

After deployment, the website is hosted on the EC2 public IP and served through a Dockerized Nginx web server.

Optional Improvements
Add a custom domain using Route 53 or Namecheap
Enable automatic container restart
Configure firewall and security settings
Add HTTPS with SSL certificates
Purpose

This project is designed for beginners who want hands-on experience with cloud deployment, Docker containers, and basic web hosting using AWS.


Here are the steps:

🧱 STEP 1: Create AWS Free Tier Account

1.	Go to: https://aws.amazon.com/free/ 

2.	Sign up and verify your account 

3.	Enable Free Tier EC2 access 
________________________________________

🖥️ STEP 2: Launch an EC2 Instance (Server)

1.	Open AWS Console → EC2 

2.	Click Launch Instance
    
Configure:

•	Name: my-web-server 

•	AMI: Amazon Linux 2023 (kernel-6.1) 

•	Instance type: t3.micro (Free tier) 
•	Key pair: 

o	Create new key pair → download .pem file

Network settings:

•	Allow:

o	✅ SSH (port 22) 

o	✅ HTTP (port 80) 

4.	Click Launch Instance 

![image](https://github.com/jcmf-9/My-first-project/blob/718025efdfdf9aa7b2dccf05a4b1fe7847f54ab8/EC2%20scr.png)

🔐 STEP 3: Connect to Your Server (Open Window CMD)

![image](https://github.com/jcmf-9/My-first-project/blob/0d230ce42fef9a9f97b84ddd4c54154233a016df/scr2.png)

![image](https://github.com/jcmf-9/My-first-project/blob/18b7054d241e694a04853cd2d37409534a6977c7/scr3.png)

Find IP in EC2 dashboard.

✅ Connect to EC2

Step 1 — Update system

sudo yum update -y
________________________________________
Step 2 — Install Docker

sudo yum install docker -y
________________________________________

Step 3 — Start Docker

sudo systemctl start docker
________________________________________

Step 4 — Enable Docker on boot

sudo systemctl enable docker
________________________________________
Step 5 — (IMPORTANT) allow ec2-user to use docker

sudo usermod -aG docker ec2-user

Then log out and log back in:

exit

Reconnect via SSH.
________________________________________
Step 6 — Test Docker

docker --version

docker run hello-world
________________________________________

🌐 STEP 5: Create Your Simple Web Page

Create folder:

mkdir mywebsite && cd mywebsite

Create HTML file:

nano index.html

copy and paste the code in the file below

[Download Here](https://github.com/jcmf-9/My-first-project/blob/e0cab187013d93b765ae75ef717a8a7b0ccec6fa/index.html)


🐳 STEP 6: Create Docker Web Server

Create Dockerfile:

nano Dockerfile

copy and paste the code in the file below

[Download Here](https://github.com/jcmf-9/My-first-project/blob/e8752eb3824f26126d67889415484ec101d5355e/Dockerfile.txt)

_____________________________________
🔨 STEP 7: Build Docker Image

docker build -t my-webpage .
________________________________________
▶️ STEP 8: Run the Container

docker run -d -p 80:80 my-webpage
________________________________________
🌍 STEP 9: Open Your Website

In browser:

http://YOUR_PUBLIC_IP

You should see your webpage 🎉
________________________________________

![image](https://github.com/jcmf-9/My-first-project/blob/a4e1cbb40f28da50041a21dd259f27f8c991c88a/output.png)


