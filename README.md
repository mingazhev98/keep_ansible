# keep_ansible

Set of ansible playbooks for deploying, monitoring and managing KEEP validator instances.

Configuration.

1) Change the ./vars/vars.yaml varaiables configuration file accordingly.
2) Create an inventory file & parse or edit the default /etc/ansible/hosts file. E.g.

[keep]
123.123.123.33

[keep:vars]
ansible_ssh_user = ansible
ansible_ssh_private_key_file = /Users/jqhils/.ssh/privatekey

Usage.
Execute the bootstrap playbook providing the required components and entering user sudo:

ansible-playbook bootstrap_keep.yaml -i hosts -K

After successfully setting up keep instances, explore the other additional playbooks

Additionally.

Once you've bootstrapped and you want to deploy a configuration change. You can run the configure_keep.yaml playbook:

ansible-playbook configure_keep.yaml -i hosts -K

Playbooks.

bootstrap_keep.yaml	-------- Installs & configures Keep-ecdsa and Keep-
configure_keep.yaml	-------- Applies configuration changes and restarts Keep-ecdsa & Keep-core
