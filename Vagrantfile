# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.

  config.ssh.insert_key = false
  config.vm.define "server" do |server|
    server.vm.box = "centos/6"
    server.vm.hostname = "server"
    server.vm.network "forwarded_port", guest: 8080, host: 8080
    server.vm.network "private_network", ip: "192.168.150.2"
#    server.vm.provision "ansible" do |ansible|
#      ansible.playbook = "playbooks/system_provision.yml"
#      ansible.limit = "go-server"
#    end
  end

  config.vm.define "client" do |client|
    client.vm.box = "centos/6"
    client.vm.hostname = "client"
#    client.vm.network "forwarded_port", guest: 8153, host: 2153
    client.vm.network "private_network", ip: "192.168.150.3"
#    agent.vm.provision "ansible" do |ansible|
#      ansible.playbook = "playbooks/system_provision.yml"
#      ansible.limit = "go-agent"
#    end
  end
end
