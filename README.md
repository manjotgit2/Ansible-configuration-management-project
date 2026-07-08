this is second project of internship
# Ansible Configuration Management Project

## Overview

This project demonstrates how to automate server configuration using Ansible. Two AWS EC2 instances were created: one as the Ansible Control Node and another as the Target Server (Managed Node). Using Ansible playbooks, Apache HTTP Server was automatically installed, configured, and started on the target server. The project highlights Infrastructure as Code (IaC) principles and automation in DevOps.

---

## Objectives

- Learn Ansible automation.
- Automate server configuration.
- Install and configure Apache automatically.
- Manage remote servers using SSH.
- Execute automation using Ansible Playbooks.
- Reduce manual effort in server administration.

---

## Technologies Used

- Ansible
- AWS EC2
- Ubuntu WSL
- Amazon Linux
- SSH
- YAML
- Apache HTTP Server
- Git
- GitHub

---

## Project Architecture

```
Local System (WSL)
        │
        │ SSH
        ▼
Ansible Control Node (EC2)
        │
        │ SSH
        ▼
Target Server (EC2)
        │
        ▼
Apache Web Server
```

---

## Project Structure

```
Ansible-configuration-management-project/
│── inventory
│── playbook.yml
│── README.md
└── screenshots/
```

---

## Implementation Steps

### Step 1 – Launch EC2 Instances

- Created two AWS EC2 instances.
- One instance acted as the Ansible Control Node.
- Second instance acted as the Target Server.
- Configured Security Groups.
- Allowed SSH (Port 22).
- Allowed HTTP (Port 80).

---

### Step 2 – Connect to Control Node

```bash
ssh -i key.pem ec2-user@<Control_Node_Public_IP>
```

---

### Step 3 – Install Ansible

```bash
sudo dnf install ansible -y
ansible --version
```

---

### Step 4 – Create Inventory File

Created an inventory file containing the target server details.

Example:

```ini
[webservers]
<Target_Public_IP> ansible_user=ec2-user ansible_ssh_private_key_file=~/key.pem
```

Verify connectivity:

```bash
ansible all -i inventory -m ping
```

---

### Step 5 – Create Playbook

Created an Ansible playbook to:

- Install Apache
- Start Apache service
- Enable Apache at boot
- Create a sample web page

Run the playbook:

```bash
ansible-playbook -i inventory playbook.yml
```

---

### Step 6 – Verify Deployment

Open the browser:

```
http://<Target_Public_IP>
```

The Apache web page should display successfully.

---

## Commands Used

```bash
ansible --version
ansible all -i inventory -m ping
ansible-playbook -i inventory playbook.yml
ssh -i key.pem ec2-user@<Public-IP>
```

---

## Screenshots

The **screenshots** folder contains:

- EC2 Instances
- SSH Connection
- Ansible Installation
- Inventory File
- Ping Module Output
- Playbook
- Playbook Execution
- Browser Output

---

## Learning Outcomes

During this project, I learned:

- Installing and configuring Ansible
- Understanding Control Node and Managed Node
- SSH-based server management
- Creating Ansible Inventory files
- Writing YAML playbooks
- Using Ansible modules
- Automating Apache installation
- Infrastructure as Code (IaC)
- Remote server configuration
- Configuration Management using Ansible

---

## Results

- Successfully launched two AWS EC2 instances.
- Successfully installed Ansible.
- Successfully established SSH communication.
- Successfully executed Ansible Playbook.
- Successfully installed and configured Apache.
- Successfully deployed the web server.
- Successfully automated server configuration.

---

## Conclusion

This project demonstrated how Ansible automates server configuration and software deployment. Using an Ansible Control Node, tasks were executed on a remote Target Server through SSH without manual intervention. The project provided practical experience with Infrastructure as Code (IaC), configuration management, automation, and remote server administration, which are essential skills in modern DevOps.

---

## Author

**Manjot Kaur**

Master of Computer Applications (MCA)

DevOps Internship Project
