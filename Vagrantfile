# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.hostname = "hadoop-master"
  config.vm.box = "bento/ubuntu-16.04"  
  config.vm.network "private_network", ip: "192.168.33.10"
  config.ssh.insert_key = false
  
  config.vm.provider "virtualbox" do |vb|
    vb.name = "hadoop-master"
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--cableconnected1", "on"]
  end
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook-hadoop-master.yml"
    ansible.sudo = true
  end

  config.vm.define :hadoop_master
end
