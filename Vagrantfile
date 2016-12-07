# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-16.04"  
  config.ssh.insert_key = false

  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = false

  config.vm.define "hadoop-master" do |hadoop_master|
    hadoop_master.vm.network "private_network", ip: "192.168.33.10"

    hadoop_master.vm.provider "virtualbox" do |vb|
      vb.name = "hadoop-master"
      vb.memory = "4096"
      vb.customize ["modifyvm", :id, "--cableconnected1", "on"]
    end

    hadoop_master.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook-hadoop-master.yml"
      ansible.sudo = true
    end
  end

  config.vm.define "hadoop-slave1" do |hadoop_slave1|
    hadoop_slave1.vm.network "private_network", ip: "192.168.33.20"

    hadoop_slave1.vm.provider "virtualbox" do |vb|
      vb.name = "hadoop-slave1"
      vb.memory = "4096"
      vb.customize ["modifyvm", :id, "--cableconnected1", "on"]
    end

    hadoop_slave1.vm.provision "ansible" do |ansible|
      ansible.playbook = "provisioning/playbook-hadoop-slave.yml"
      ansible.sudo = true
    end
  end

end
