# Project Name: Jenkins Pipeline to install Nginx 
Description: Installing Nginx on aws ec2 instance using Ansible as configuration management using Jenkins pipeline.

# Tech Stack:
1. Ansible
2. AWS
3. Jenkins
4. Github

# Features
1. Automated Nginx installation using Ansible
2. CI/CD pipeline using Jenkins
3. Version control with GitHub

# Github Repo link: https://github.com/Hi-Lalit/nginx-install.git

- This git repo having two branches:

1. main
2. feature

# Structure of Project is: 

NGINX-INSTALL
├── inventory.yml
├── Jenkinsfile
├── nginx-playbook.yml
└── README.md

# Prerequisites

- Make sure you have:

1. Ansible installed
2. AWS EC2 instance
3. Jenkins installed
4. SSH key configured between Jenkins and EC2

# To run this project locally clone this: git clone https://github.com/Hi-Lalit/nginx-install.git
- cd NGINX-INSTALL
- command to run this playbook- ansible-playbook nginx-playbook.yml


* By: Lalit Kumar Gautam *