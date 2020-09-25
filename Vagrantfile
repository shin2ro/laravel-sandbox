# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vm|
    vm.memory = 2048
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/site.yml"
  end
end

