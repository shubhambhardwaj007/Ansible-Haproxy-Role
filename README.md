# Ansible-Haproxy-Role
## Lets understand the Problem Statement:
1. Create an Ansible Role to Install Haproxy LoadBalancer Software on Remote system.
2. Dynamically update the Haproxy configuration file with BackEnd Webserver IP Addresses.
3. Start Haproxy LoadBalancer Service and make Haproxy LoadBalancer Service permanent on reboot.
4. Add Idempotence to Haproxy LoadBalancer such that on new Changes are made to Haproxy LoadBalancer Configuration file, Haproxy LoadBalancer Service restarts automatically.
## To replicate same setup on your Local Machine perform following steps:
- Install Ansible on local system and this local machine acts as `Master Node`.
- Clone this repository on Local Machine and edit `ansible.cfg` file to add up location where our Role is present using `roles_path` keyword.
- Now create Inventory File and Playbook for running this role.Specify Inventory Location in Inventory using `inventory`.
- Note that Inventory File must have all Webserver IP Addresses/Domain Name under HostGroup Name `webserver` and all LoadBalancer IP Address/Domain Name under HostGroup Name `loadbalancer`.
- Edit `Ansible-Haproxy-Role/vars/main.yml` file to tell about Exposed Haproxy LoadBalancer Port Number using variable `exposed_port_number`.
- Edit `Ansible-Haproxy-Role/vars/main.yml` file to tell about  Backend Webserver Port Number using variable `webserver_port`
### Finally all things set so it's time to Deploy above complete setup and run below command:
> ansible-playbook <name_of_playbook>
