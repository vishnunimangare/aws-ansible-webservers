# aws-ansible-webservers
 Install and configure Nginx on Amazon Linux 2023 EC2 instances using ansible
 🚀 Automated Nginx Deployment on AWS EC2 Using Ansible

I recently completed an automation project where I deployed an Nginx web server on an AWS EC2 instance using Ansible.
I configured one EC2 instance as the Ansible controller/host and another instance as the target web server.

This project helped me practice Infrastructure as Code, AWS, Linux automation, and DevOps best practices.

📁 Project Directory Structure
[ec2-user@ip-172-31-69-13 ~]$ tree
.
├── ansible.cfg
├── aws
│   └── ansible.pem
├── aws-ansible-webservers
│   ├── LICENSE
│   ├── README.md
│   └── nginx.yml
├── inventory
│   └── hosts
└── playbooks
    ├── nginx.yml
    ├── ping.yml
    └── uptime.yml

⚙️ Ansible Configuration (ansible.cfg)
[defaults]
inventory = ./inventory
remote_user = ec2-user
private_key_file = aws/ansible.pem
host_key_checking=False
retry_files_enabled=False

[privilege_escalation]
become = true
become_method = sudo
become_user = root
become_ask_pass = false

🌍 Inventory File (hosts)
[all]
172-31-69-13
18.210.28.143
[web]
18.210.28.143

📜 Nginx Playbook Tasks (nginx.yml)

The playbook performs the following operations on the target server:

✔️ Update all system packages
✔️ Install the Nginx package
✔️ Ensure Nginx service is running and enabled at boot
✔️ Deploy a custom index.html page

Executed using below command:

sudo ansible-playbook -i inventory/hosts playbooks/nginx.yml

🌐 Deployment Verification

Successfully deployed and verified Nginx by visiting:
👉 http://18.210.28.143

📦 GitHub Repository

All configuration files and playbooks are available here:
🔗 https://github.com/vishnunimangare/aws-ansible-webservers

This was a great hands-on experience with Ansible automation, AWS EC2, and web server deployment. Excited to explore more automation workflows and build scalable cloud environments! 🔥

#AWS #Ansible #DevOps #Automation #Nginx #IaC #EC2 #CloudEngineering #Linux
