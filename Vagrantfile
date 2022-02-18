# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
 
    config.vm.provision "shell", inline: <<-SHELL
        apt-get update -y
        echo "10.0.0.20  master-node" >> /etc/hosts
    SHELL
    config.vm.provision "shell", path: "C:/genesis/scripts/setings_machine.sh"
    config.vm.define "master" do |master|
      master.vm.box = "bento/ubuntu-18.04"
      master.vm.hostname = "master-node"
      master.vm.network "private_network", ip: "10.0.0.20"
      master.vm.provider "virtualbox" do |vb|
          vb.memory = 2048
          vb.cpus = 2
      end
    end
end  