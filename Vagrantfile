# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  ENV['VAGRANT_NO_PARALLEL'] = 'yes'

  config.vm.provider :vmware_esxi do |esxi|
    esxi.esxi_hostname = "#{ENV['ESXI_HOSTNAME']}"
    esxi.esxi_username = "#{ENV['ESXI_USERNAME']}"
    esxi.esxi_password = 'env:ESXI_PASSWORD'
  end

  # Master node where ansible will be installed
  config.vm.define "controller" do |controller|
    controller.vm.box = "dma65ml/ubuntu20.04"
    controller.vm.box_version = "1.0"
    controller.vm.hostname = "controller.anslab.com"
    controller.vm.network "private_network", ip: "192.168.1.150"
    controller.vm.provision "shell", path: "bootstrap.sh"
    controller.vm.provision "file", source: "key_gen.sh", destination: "/home/vagrant/"
    controller.vm.synced_folder('.', '/Vagrantfiles', type: 'rsync')
  end

  # Managed node 1.
  config.vm.define "m1" do |m1|
    m1.vm.box = "dma65ml/ubuntu20.04"
    m1.vm.box_version = "1.0"
    m1.vm.hostname = "managed1.anslab.com"
    m1.vm.network "private_network", ip: "192.168.1.151"
    m1.vm.provision "shell", path: "bootstrap.sh"
    m1.vm.synced_folder('.', '/Vagrantfiles', type: 'rsync')
  end

  # Managed node 2.
  config.vm.define "m2" do |m2|
    m2.vm.box = "dma65ml/ubuntu20.04"
    m2.vm.box_version = "1.0"
    m2.vm.hostname = "managed2.anslab.com"
    m2.vm.network "private_network", ip: "192.168.1.152"
    m2.vm.provision "shell", path: "bootstrap.sh"
    m2.vm.synced_folder('.', '/Vagrantfiles', type: 'rsync')
  end

end
