# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define 'dev' do |dev|
    # comment following three lines until you provision the server and actually create bbw user
    # dev.ssh.username = 'bbw'
    # dev.ssh.private_key_path = '~/.ssh/id_rsa'
    # dev.vm.synced_folder './', '/var/apps/bbw/current', owner: 'bbw', group: 'bbw'

    dev.vm.box = 'trusty32'
    dev.vm.network :forwarded_port, guest: 3000, host: 3000
    dev.vm.network :private_network, ip: '192.168.3.10'
  end

  config.vm.define 'production' do |production|
    production.vm.box = 'trusty32'
    production.vm.network :private_network, ip: '192.168.3.11'
  end

#  config.vm.provision 'ansible' do |ansible|
#    ansible.playbook = 'ansible/playbook.yml'
#    ansible.inventory_path = 'ansible/hosts'
#    ansible.verbose = 'v'
#  end
end
