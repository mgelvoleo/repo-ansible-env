Tutorial

Make the ansible easier when doing automate

Make a file ansible.cfg content is

[defaults]
inventory = inventory
private_key_file = ~/.ssh/ansible 


after execute the command
> ansible all -m ping


Display the ip of host by this command
> ansible all --list-hosts


To display all the info of all servers
>ansible all -m gather_facts

To display specific infor of server
> ansible all -m gather_facts --limit 172.16.0.10



To perfome the command by not using sudo in server
> ansible all -m apt -a update_cache=true --become --ask-become-pass

Install package to each server
> ansible all -m apt -a name=tmux --become --ask-become-pass

To update the specific packages example snap
> ansible all -m apt -a "name=snap state=latest" --become --ask-become-pass

