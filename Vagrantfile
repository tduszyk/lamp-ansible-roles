# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/rockylinux8"
  config.vm.hostname = "lamp.test"
  config.vm.network :private_network, ip: "192.168.56.15"
  config.ssh.insert_key = false
  config.vm.provision "file", source: ".ssh/authorized_keys", destination: "~/.ssh/authorized_keys"
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory = 512
  end

  # Ansible provisioner.
  #config.vm.provision :ansible do |ansible|
  #  ansible.playbook = "provisioning/playbook.yml"
  #end
end
