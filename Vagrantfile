# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "demystify-go.example.org"
  config.vm.synced_folder "go", "/usr/src/go"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.name = "[Vagrant] Demystify Go"
    vb.cpus = "1"
    vb.memory = "1024"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.playbook = "main.yml"
    ansible.provisioning_path = "/vagrant/ansible"
  end
end
