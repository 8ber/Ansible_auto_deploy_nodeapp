# Ansible - Auto deploy node application

This is a simple Ansible-playbook that automates the deployment of a NodeJS application on most of the **Debian based Linux distributions (i.e., those that include apt)**. The playbook also basically validates that the node process is running.

The playbook is replacing the manual labor of sshing into a remote server and updating apt, installing npm and NodeJS, create a new Linux user to run the app, unpack the artifact (.tgz), install the application dependencies, start the application and check that its actually running. 

Note: this playbook is **NOT** meant to be used on AWS Linux images.

## Usage and installation 

**make sure:**
1. your local machine has ansible installed. 
2. your Linux target server has python installed (preferably version 3).
3. verify/configure ssh connection from your local machine to the target server.

to install:

4. Edit the hosts file:
`*** ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_user=root` replace "***" with your target server ip.
5. edit the vars file (yaml syntax).
6. in your local terminal:
```bash
ansible-playbook deploy-node.yaml
```

### Featured modules:

- apt
- unarchive
- shell
- user
- npm
- command
- async & poll
- debug

Further usages and parameters of the listed modules, can be found at the official [Ansible documentation](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/).
