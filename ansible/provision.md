# Before provision
We provision servers by "ansible" tool. This tool connects to servers by ssh under `ansible` user. So `ansible` user should has sudo rights.

1. Create 'ansible' user

    $ sudo adduser ansible
    ...
    Enter new UNIX password: 
    Retype new UNIX password:
    ...

2. Add 'ansible' user to sudoers with privilege run all commands
   with no password entering

    $ sudo nano /etc/sudoers
   
   And insert the following line in `User privilege specification` section

    ansible ALL=NOPASSWD:ALL

3. Copy you public key to servers (for not entering ansible password every time when ansible connects by ssh)

    $ ssh-copy-id -i ~/.ssh/id_rsa.pub ansible@servername

# Provision
ansible-playbook ansible/playbook.yml -i ansible/hosts
