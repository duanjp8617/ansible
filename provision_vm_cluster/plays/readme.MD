This folder contains ansible plays for provisioning a small VM cluster.

## Before using these plays:
1. Make sure that you have several available servers.
2. In an ideal scenario, the servers should be connected to two separate LAN networks. Each server should have one additional network interface that is dedicated to Internet connectivity.
3. Follow the intrustions from the BridgeNetwork section of my personal emacs-config repo, create two bridge interfaces, and connect the bridge interfaces to the physical network interfaces that are attached to the LAN network. 
4. Following the intstructions from the QuickVM section of my personal emacs-config repo, and create a base VM image.
3. According to your hardware settings, modify the parameters in roles/load_vars, plays/config_bridge_networks.yml and plays/upload_my_hosts.yml

## Provision steps:
1. become_hypervisor.yml (with sudo priviledge)
2. create_nat_network.yml
3. create_vms.yml
4. check_bootup.yml
5. config_bridge_networks.yml (with sudo priviledge)
6. upload_vm_hosts.yml

## Using the VMs
Log into the target machine of upload_vm_hosts.yml play, copy the work_space_dir/vm_hosts file to /etc/ansible/hosts, then use the following command to test the availability of the VMs:

ansible vms -m ping

## Clean out VMs and networks:
1. delete_vms.yml
2. delete_nat_network.yml