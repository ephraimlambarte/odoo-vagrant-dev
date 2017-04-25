# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrant.configure version 2.
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  # -----------------------------------------------------------------------------------------------
  # Port forwarding
  # -----------------------------------------------------------------------------------------------

  # PostgreSQL port for remote admin on the host
  config.vm.network :forwarded_port, host: 5432, guest: 5432, host_ip: "127.0.0.1"

  # Odoo port for remote admin on the host
  config.vm.network :forwarded_port, host: 8069, guest: 8069, host_ip: "127.0.0.1"
  config.vm.network :forwarded_port, host: 8072, guest: 8072, host_ip: "127.0.0.1"

  # Mail Catcher port for remote admin on the host
  config.vm.network :forwarded_port, host: 1080, guest: 1080, host_ip: "127.0.0.1"
  config.vm.network :forwarded_port, host: 25, guest: 25, host_ip: "127.0.0.1"

  # Jupyter port for remote admin on the host
  config.vm.network :forwarded_port, host: 8888, guest: 8888, host_ip: "127.0.0.1"

  # -----------------------------------------------------------------------------------------------
  # Virtual Box Settings (Docs: Docs: http://docs.vagrantup.com/v2/virtualbox/configuration.html)
  # -----------------------------------------------------------------------------------------------
  config.vm.provider "virtualbox" do |vb|
   vb.gui = false
   vb.memory = "3000"
   vb.name = "Odoo Local Dev Environment"
   vb.cpus = 4
  end

  # -----------------------------------------------------------------------------------------------
  # Shell provisioning (Docs: http://docs.vagrantup.com/v2/provisioning/shell.html)
  # -----------------------------------------------------------------------------------------------
  config.vm.provision "shell", path: "bootstrap.sh"
end
