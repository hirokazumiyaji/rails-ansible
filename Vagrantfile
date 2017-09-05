# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.3"
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 80, host: 8000
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "webservers.yml"
    ansible.inventory_path = "inventories/development"
    ansible.limit = "all"
  end
end
