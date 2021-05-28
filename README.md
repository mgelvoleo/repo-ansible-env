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
