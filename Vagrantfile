# -*- mode: ruby -*-
# vi: set ft=ruby :
#https://app.vagrantup.com/gusztavvargadr/boxes/windows-10
Vagrant.configure("2") do |config|
  config.vm.define "windows10" do |windows10|
    config.vm.box = "gusztavvargadr/windows-10"
    windows10.vm.hostname = 'windows10'
    config.vm.network "private_network", ip: "172.28.128.110"
    #config.vm.network "private_network", :type => 'dhcp', ip: "172.28.128.3"
    windows10.vm.synced_folder "./share", "/home/vagrant/share", create: true
    #windows10.vm.provision "ansible" do |ansible|
    #  ansible.playbook = "playbook.yml"
    #end

#    windows10.vm.network :private_network, ip: "192.168.56.101"
    windows10.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 2048]
      v.customize ["modifyvm", :id, "--name", "windows10"]
      v.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end
end

