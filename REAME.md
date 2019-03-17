0. Unpack the archive.
1. Ensure Ansible is installed. The deliverable was tested with Ansible 2.7 on top of ubuntu/cosmic64
2. Populate ansible/inventory_mintos with desired variable for:
2.1. ansible_user
2.2. ansible_ssh_private_key_file
2.3. ansible_python_interpreter (facts gathering)
2.4. DNS names and/or ip addresses of the hosts
3. Review the variables 
3.1. at ansible/group_vars/all.yml
3.2. at ansible/group_vars/vaulted/vault_all.yml (ansible-vault view ansible/group_vars/vaulted/vault_all.yml)
4. Download and install Ansible-galaxy roles:
sudo ansible-galaxy install geerlingguy.mysql
sudo ansible-galaxy install geerlingguy.php
sudo ansible-galaxy install geerlingguy.apache
sudo ansible-galaxy install geerlingguy.apache-php-fpm
sudo ansible-galaxy install geerlingguy.composer
5. Run the playbook:
cd ansible && ansible-playbook -i inventory_mintos mintos-hw.yml --ask-vault-pass
Password: mintospass
6. Open the webpage at the host, specified at 2.4:
http://<desired-hostname>/