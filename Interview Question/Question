1. What is Ansible and how does it work?

Ansible is an open-source automation tool used for configuration management, application deployment, and task automation.
It works by connecting to managed nodes (servers) via SSH and pushes small programs called modules to execute tasks.
Since it is agentless, there is no need to install any software on the target systems.

2. What are ad-hoc commands?

Ad-hoc commands are one-time Ansible commands used to perform simple tasks like rebooting servers, copying files, or installing packages without writing a playbook.
Example:

ansible all -m shell -a "uptime"

3.How do you secure sensitive data in Ansible?

Sensitive data like passwords, API keys, or certificates can be secured using Ansible Vault.
Vault allows you to encrypt entire files or variables. Example to create an encrypted file:

ansible-vault create secrets.yml

5. What is Ansible Tower?

Ansible Tower is a web-based interface and dashboard for Ansible.
It provides:

    Role-based access control (RBAC)

    Job scheduling

    Centralized logging

    Visual inventory management

    API for external integrations
    It helps manage complex deployments easily and securely.


6. How does Ansible ensure idempotency?

Ansible modules are designed to be idempotent, meaning running the same task multiple times will not change the system after the first successful execution.
Example: Installing a package with apt will not reinstall it if it's already installed.

7. Can you explain the role of handlers in Ansible?

Handlers are special tasks that only run when notified.
They are usually triggered after a change occurs in a task.
Example use case: Restarting a service after configuration changes.

- name: Restart nginx
  service:
    name: nginx
    state: restarted
  listen: "restart nginx"

8. How would you integrate Ansible with AWS?

To integrate with AWS:

    Install the boto3 Python library.

    Install AWS Ansible collections (e.g., amazon.aws).

    Configure AWS credentials (using aws configure or environment variables).

    Use modules like amazon.aws.ec2_instance or amazon.aws.s3_bucket inside playbooks.

9. How to debug an Ansible playbook?

    Use verbose mode:

ansible-playbook playbook.yml -v
ansible-playbook playbook.yml -vvv   # Very detailed output

Use debug module inside the playbook:

    - name: Show a variable
      debug:
        var: my_variable

    Check YAML syntax carefully (spaces matter).

10. What are facts in Ansible?

Facts are system information collected about the managed nodes at runtime.
Examples: IP address, OS type, memory, CPU, hostname.
They are automatically gathered at the start of playbook execution and can be used inside tasks.

Example:

- debug:
    var: ansible_facts['os_family']


