# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  # Box Name
  config.vm.box = "centos6.7"
  
  # Network
  config.vm.network "private_network", ip: "192.168.33.10"
  
  # Synced Folder
  config.vm.synced_folder "/path/to/directory", "/var/www/html",
    :owner => "apache",
    :group => "apache",
    :mount_options => ["dmode=775,fmode=664"]
  
  # Provider(Optional)
  config.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--paravirtprovider", "kvm"]
  end
  
  # Host Updater
  config.vm.network :private_network, ip: "192.168.33.10"
  config.vm.hostname = "localdev" 
  config.hostsupdater.aliases = ["localdev-hoge"]
  
  # xdebug(Optional)
  config.vm.network :forwarded_port, host: 3000, guest: 3000
end
