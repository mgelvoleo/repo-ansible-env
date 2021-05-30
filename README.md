Tutorial

Make the ansible easier when doing automate

Make a file ansible.cfg content is

[defaults]
inventory = inventory
private_key_file = ~/.ssh/ansible 


after execute the command
~> ansible all -m ping


Display the ip of host by this command
~> ansible all --list-hosts


To display all the info of all servers
~>ansible all -m gather_facts

To display specific infor of server
~> ansible all -m gather_facts --limit 172.16.0.10


First Playbook
Install the package apache2

install_playbook.yml

---

- hosts: all
  become: true
  tasks:

  - name: install apache2 packages
    apt:
      name: apache2   


Then run the playbook file with this command
> ansible-playbook --ask-become-pass install_playbook.yml




To Remove the pakages

---

- hosts: all
  become: true
  tasks:

  - name: install apache2 packages
    apt:
      name: apache2  
      state: absent
  
  - name: install php support for apache
    apt:
      name: libapache2-mod-php
      state: absent

Run on this command
> ansible-playbook --ask-become-pass remove_playbook.yml