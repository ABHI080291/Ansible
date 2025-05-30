**Configuration Management** - Configuration Management is the process of maintaining systems, such as computer hardware and software, in a desired state. Configuration Management (CM) is also a method of ensuring that systems perform in a manner consistent with expectations over time.

**Diffrent types of Congiguration Management Tools :-**
  1) Ansible.
  2) Chef.
  3) Puppet.

**Ansible vs Other Tools**

![image](https://github.com/user-attachments/assets/70e79230-c16f-4689-af76-3b0372255903)

**What is Ansible?**

Ansible is an open-source automation tool used for configuration management, application deployment, and task automation. It simplifies complex tasks and orchestrates multiple systems efficiently.

**Why use Ansible?**

1) Agentless (uses SSH).
2) Simple YAML syntax.
3) Idempotent operations.
4) Integration with cloud providers (AWS, Azure, GCP).
 
**Features of Ansible**
Open-source, Minimal Learning Curve, Highly Secure, Extensible

** How Ansible Works**
1) Ansible uses SSH for communication
2) No agent installation on managed nodes.
3) Tasks are defined in YAML playbooks.
4) Ansible pushes small programs (modules) to managed nodes.

**Key Components**
Modules:- Reusable scripts for tasks like installing packages.
Playbooks:- Files written in YAML that define a series of tasks.
Tasks:- Individual actions to perform on a host.
Roles:- Organized collections of tasks, variables, templates, and handlers.
Handlers:- Triggered by a notifier, usually after a task changes.
Variables:- Dynamic values used in tasks.

**Ansible Installation**
**On Ubuntu**
1) sudo apt-add-repository ppa:ansible/ansible
2) sudo apt update
3) sudo apt install ansible

**On Windows (Using WSL)**
1) Install Ubuntu WSL
2) Follow Ubuntu steps

**Basic Ansible Commands**
1) ansible all -m ping
2) ansible all -m shell -a 'uptime'
3) ansible all -m copy -a 'src=/etc/hosts dest=/tmp/hosts'

**Writing Your First Playbook**

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

** Advanced Concepts**
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

**Ansible Roles (Best Practice)**
roles/role_name/tasks/main.yml
roles/role_name/handlers/main.yml

** Integrating Ansible with Cloud**

AWS
Install boto3
Use amazon.aws.ec2 modules

Azure
Install azure.azcollection
Use azure_rm_virtualmachine module


**Real-World Use Cases**
Setting up a LAMP stack
Rolling application updates
Backup and recovery automation

**Troubleshooting Ansible**
Use -v, -vv, -vvv for verbose output
Check ansible.cfg
Validate YAML syntax

**Best Practices**
Separate configuration and code
Use roles for reusability
Keep playbooks short and readable
Version control using Git
