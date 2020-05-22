This folder contains ansible plays for provisioning a small VM cluster.

## Before using these plays:
1. Make sure that you have several available servers.
2. In an ideal scenario, the servers should be connected to two separate LAN networks. Each server should have one dedicated network interface that provides Internet connection.
3. Follow the intrustions from the BridgeNetwork section of my personal emacs-config repo, and connect the LAN network interfaces two bridges.
4. Following the intstructions from the QuickVM section of my personal emacs-config repo, and create a base VM image.
3. According to your hardware settings, modify the parameters in roles/load_vars, plays/config_bridge_networks.yml and plays/upload_my_hosts.yml

## Provision steps:
1. become_hypervisor.yml
2. create_nat_network.yml
3. create_vms.yml
4. check_bootup.yml
5. config_bridge_networks.yml (with sudo priviledge)
6. upload_vm_hosts.yml

## Clean out VMs and networks:
1. delete_vms.yml
2. delete_nat_network.yml