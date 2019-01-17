# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
 
  config.vm.box = "centos/7"

  config.vm.hostname = "jenkins"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.synced_folder "../jenkins", "/home/vagrant/jenkins", type: "virtualbox"
  config.vm.synced_folder "../jenkins-apps", "/home/vagrant/jenkins-apps", type: "virtualbox"
 
  config.vm.provider "virtualbox" do |vb|
    vb.name = "Jenkins Server"
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo service jenkins restart
  SHELL
end
