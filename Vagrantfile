# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|

  config.vm.box = "thdengops/ubuntu-14.04-dev"
  config.vm.hostname = "danknodes"
  config.vm.network :private_network, ip: "192.168.88.33", netmask: "255.255.255.0"
  config.vm.boot_timeout = 1200

  config.vm.synced_folder "../nodeproject", "/var/www/nodeproject",
  type: "nfs"
    config.vm.provision "shell", inline: <<-SHELL
    sudo timedatectl set-timezone America/Los_Angeles
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
    echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
    sudo apt-get update
    sudo apt-get install -y mongodb-org
    sudo apt-get install vim

  SHELL

end
