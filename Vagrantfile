# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  # Box Name
  config.vm.box = "centos6.7"
  
  # Time Setting
  config.vm.provider :virtualbox do |vb|
        vb.customize ["setextradata", :id, "VBoxInternal/Devices/VMMDev/0/Config/GetHostTimeDisabled", 0]
  end
  
  # Synced Folder
  config.vm.synced_folder "/path/to/directory", "/var/www/html",
    :owner => "apache",
    :group => "apache",
    :mount_options => ["dmode=775,fmode=664"]
  
  # Provider(Optional)
  config.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--paravirtprovider", "kvm"]
  end

  # Memory
  config.vm.provider "virtualbox" do |vm|
    vm.memory = 1024
  end
  
  # Network - Host Updater
  config.vm.network :private_network, ip: "192.168.33.10"
  config.vm.hostname = "localdev" 
  config.hostsupdater.aliases = ["localdev-hoge"]
  
  # xdebug(Optional)
  config.vm.network :forwarded_port, host: 3000, guest: 3000
end
