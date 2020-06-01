This folder contains an ansible play for turning the target machine into a development machine for Rust code.

## Before using the play:
1. Make sure that the target machine is connected to the private LAN network of the VM cluster provisied with the plays from provision_vm_cluster.
2. Update the parameters contained in roles/load_vars/vars directory. In particular, change the value of "remote_repo" to a valid git repo which contains valid Rust source code for development. Change the parameters contained cargo_crates.yml to pre-install necessary Cargo crates.
3. Make sure that the target machine has enough memories for building Rust source code.

## Using the dev machine.
1. Open vscode and use remote ssh extention to connect to the dev machine.
2. Install vscode rust extention, and set the "rustupPath" field to the value of "rustup_bin_path" variable from the load_vars role.
3. You can begin the development process using the plays contained in simple_ci.