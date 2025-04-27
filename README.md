# ANSIBLE :-


**1. Introduction**

**What is Ansible?**

Ansible is an open-source automation tool used for configuration management, application deployment, and task automation. It simplifies complex tasks and orchestrates multiple systems efficiently.

**Why use Ansible?**

A) Agentless (uses SSH)
B) Simple YAML syntax
C) Idempotent operations
D)Integration with cloud providers (AWS, Azure, GCP)

**Features of Ansible**
Open-source
Minimal Learning Curve
Highly Secure
Extensible

**2. How Ansible Works**
Ansible uses SSH for communication.
No agent installation on managed nodes.
Tasks are defined in YAML playbooks.
Ansible pushes small programs (modules) to managed nodes.

**3. Key Components**
Modules:- Reusable scripts for tasks like installing packages.
Playbooks:- Files written in YAML that define a series of tasks.
Tasks:- Individual actions to perform on a host.
Roles:- Organized collections of tasks, variables, templates, and handlers.
Handlers:- Triggered by a notifier, usually after a task changes.
Variables:- Dynamic values used in tasks.


4. Ansible Installation

**On Ubuntu**
sudo apt-add-repository ppa:ansible/ansible

sudo apt update

sudo apt install ansible

**On Windows (Using WSL)**
Install Ubuntu WSL

Follow Ubuntu steps

**5. Basic Ansible Commands**
ansible all -m ping

ansible all -m shell -a 'uptime'

ansible all -m copy -a 'src=/etc/hosts dest=/tmp/hosts'

**6. Writing Your First Playbook**

Playbook Structure

- hosts: all
  
  become: yes
  
  tasks:
  
    - name: Install Apache
      apt:
      
        name: apache2
      
        state: present

YAML Basics
Indentation matters
Use - for list items

**7. Advanced Concepts**
Variables and Facts
Use vars: or gather system facts.
Conditionals
when: ansible_os_family == "Debian"

Loops

with_items:
  - nginx
  - apache2

Error Handling
Use block, rescue, and always.
Vault
Encrypt sensitive data.
ansible-vault create secrets.yml

**8. Ansible Roles (Best Practice)**
roles/role_name/tasks/main.yml
roles/role_name/handlers/main.yml

**9. Integrating Ansible with Cloud**

AWS
Install boto3
Use amazon.aws.ec2 modules

Azure
Install azure.azcollection
Use azure_rm_virtualmachine module

**10. Ansible Tower (Overview)**

Web UI for Ansible
Role-based access
Centralized logging

**11. Real-World Use Cases**
Setting up a LAMP stack
Rolling application updates
Backup and recovery automation

**12. Troubleshooting Ansible**
Use -v, -vv, -vvv for verbose output
Check ansible.cfg
Validate YAML syntax

**13. Best Practices**
Separate configuration and code
Use roles for reusability
Keep playbooks short and readable
Version control using Git

**14. Ansible vs Other Tools**

![image](https://github.com/user-attachments/assets/70e79230-c16f-4689-af76-3b0372255903)

