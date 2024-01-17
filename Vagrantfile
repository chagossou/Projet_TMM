# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

 
  #
  # config.vm.provider "virtualbox" do |vb|
   #config.vm.network "private_network", ip: "192.168.56.105", virtualbox__intnet: true
   config.vm.network "private_network", type: "dhcp", netmask: "255.255.255.0", dhcp_ip:"192.168.56.100", dhcp_lower: "192.168.56.101", :dhcp_upper=>"192.168.56.254"  
   config.vm.provision "docker"
   config.vm.provision "shell", inline: <<-SHELL
      sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
      sudo chmod +x /usr/local/bin/docker-compose 

      # Récupération du fichier docker-compose
      git clone https://github.com/chagossou/Projet_TMM.git 
      cd Projet_TMM
      docker-compose up -d
   SHELL
   #end
end
