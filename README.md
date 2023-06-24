# Ansible

This repository documents my experiences and processes in using Ansible.

## References

* [Ansible](https://www.ansible.com/)
* [Ansible documentation](https://docs.ansible.com/ansible/latest/index.html)

## [Installing Ansible on Ubuntu 20.04 LTS](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu)

```bash
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
```

* [Ansible Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html#installation-guide)

## [Create an inventory](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html#how-to-build-your-inventory)

Create an inventory by adding the IP or domain name to `/etc/ansible/hosts`.

```ini
[AWS_EC2]
192.168.0.1
```

Verify the hosts in inventory.

```bash
ansible all --list-hosts
```

## [Setup Ansible Config](https://docs.ansible.com/ansible/latest/reference_appendices/config.html#ansible-configuration-settings)

Create a config file in `/etc/ansible/ansible.cfg`.

```ini
[defaults]
private_key_file=/path/to/ssh_private_key.pem
remote_user=ubuntu
```

## Setup SSH connections
Add public SSH key to the `authorized_keys` file of vm.

```bash
ssh -i key.pem ubuntu@192.168.0.1
```

Verify the connection.

```bash
ansible all -m ping
```