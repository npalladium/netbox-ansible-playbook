# NetBox Ansible Playbook
> Playbook to setup NetBox on a host

## Installation

You need to have Ansible installed on your local system (or whichever "admin" server you choose). Ansible is "agentless", using SSH to push changes to remote resources. The only requirements for the remote resource are that a Python interpreter be installed and SSHD be running.

Clone this repository onto your local system with the following command:

```sh
git clone --recurse-submodules git@github.com:npalladium/netbox-ansible-playbook.git
```
A normal git clone will not work as this repo uses submodules. 

if you want to clone and update the submodules to their latest revision:
```sh
git clone --recurse-submodules --remote-submodules git@github.com:npalladium/netbox-ansible-playbook.git
```

Alternatively, the roles can be installed using ansible-galaxy.

## Usage example

* Change the `inventory` file to point towards your server. 
* Run `ansible-playbook site.yml -i inventory`.

If you are not running as a root user on the remote server, you will have to use `ansible-playbook site.yml -i inventory --extra-vars "ansible_sudo_pass=yourPassword"` or add a `ansible_sudo_pass='yourPassword'` variable to the inventory file.

## Built With

* [ansible-role-netbox](https://github.com/lae/ansible-role-netbox)
* [ansible-role-redis](https://github.com/geerlingguy/ansible-role-redis)
* [ansible-role-postgresql](https://github.com/geerlingguy/ansible-role-postgresql)
* [ansible-role-nginx](https://github.com/geerlingguy/ansible-role-nginx)

## Authors

* **Nikhil P** - *Initial work* - [npalladium][https://github.com/npalladium]

## License

This project is licensed under GNU Affero General Public License v3.0 or later.
