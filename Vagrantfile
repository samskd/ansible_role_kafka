# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "geerlingguy/ubuntu1604"
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "2048"

    config.vm.network :forwarded_port, guest: 9092, host: 9092
    config.vm.provision "ansible" do |ansible|
      ansible.galaxy_role_file = "requirements.yml"
      ansible.tags = "deploy,restart"
      ansible.playbook = "install.yml"
      ansible.extra_vars = {
        "kafka_broker_id": 1,
        "kafka_listen_address": "localhost"
      }
    end
  end
end
