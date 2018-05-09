# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/ubuntu1604"
  config.vm.network :private_network, ip: "192.168.88.8"
  config.vm.hostname = "rails-server.dev"

  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 256
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    # Run commands as root.
    ansible.sudo = true
  end
end
