# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ph20/blackarch-core-x86_64"

  config.vm.network "private_network", :type => 'dhcp'

  config.vm.provider "virtualbox" do |vb|
    vb.customize ['modifyvm', :id, '--cableconnected1', 'on'] 
  end

  config.vm.provision :ansible_local do |ansible|
    ansible.install = true
    ansible.verbose = true
    ansible.limit = "all"
    ansible.playbook = "ansible/site.yml"
    ansible.inventory_path = "ansible/inventory"
  end
end
