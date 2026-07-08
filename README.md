# Ansible Configuration Management Project

## Overview

This project demonstrates how to automate server configuration using Ansible. Two AWS EC2 instances were created: one as the Ansible Control Node and the other as the Target Server (Managed Node). Using Ansible Playbooks, Apache HTTP Server was automatically installed, configured, and deployed on the target server through SSH.

---

## Objectives

- Learn Ansible automation.
- Automate server configuration.
- Install and configure Apache HTTP Server.
- Manage remote servers using SSH.
- Execute automation using Ansible Playbooks.

---

## Technologies Used

- Ansible
- AWS EC2
- Amazon Linux
- Ubuntu (WSL)
- SSH
- YAML
- Apache HTTP Server
- Git & GitHub

---

## Project Architecture

```text
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
Apache HTTP Server
```

---

## Project Structure

```text
Ansible-configuration-management-project/
│── inventory
│── playbook.yml
│── screenshots/
└── README.md
```

---

## Features

- Automated Apache installation
- Passwordless SSH authentication
- Inventory-based server management
- YAML Playbook automation
- Infrastructure as Code (IaC)

---

## Commands Used

```bash
ansible --version
ansible all -i inventory -m ping
ansible-playbook -i inventory playbook.yml
```

---

## Screenshots

Project screenshots are available in the **screenshots/** folder.

---

## Learning Outcomes

- Configuration Management using Ansible
- Infrastructure as Code (IaC)
- Remote server automation
- SSH-based server management
- Apache web server deployment
- YAML Playbook development

---

## Author

**Manjot Kaur**

MCA Student

DevOps Internship Project
