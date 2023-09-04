# Ansible Lab Using Vagrant And Virtualbox
forked from [KarthickSudhakar/Ansible_lab_vagrant_virtualbox](https://github.com/KarthickSudhakar/Ansible_lab_vagrant_virtualbox)


This repository contains three node ansible lab setup using vagrant and esxi as the provider.

|    Node Type   | Node Name             |   IP Address  |    OS Flavor       |
| ---------------| --------------------- |---------------|--------------------|
| Controller Node| controller.anslab.com | 192.168.1.150 | dma65ml/ubuntu20.04|
| managed Node   | managed1.anslab.com   | 192.168.1.151 | dma65ml/ubuntu20.04|
| managed Node   | managed2.anslab.com   | 192.168.1.152 | dma65ml/ubuntu20.04|

The detailed explanation on how to use the lab in OsTechnix website. You can access it using the below link.

https://ostechnix.com/ansible-lab-setup-with-vagrant-and-virtualbox-in-linux/

## Build Ansible Lab Setup
\
`vagrant up`

## Post-Install Script
\
`vagrant ssh controller`\
`cd /home/vagrant/`\
`bash key_gen.sh`
