# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "puppetlabs/centos-7.0-64-nocm"
  
  config.vm.define "ssp" do |app|
    app.vm.hostname = "ssp"
    app.vm.network "private_network", ip: "192.168.66.4", :netmask => "255.255.255.0"
    app.vm.provider "vmware_fusion" do |v|
      v.vmx["memsize"] = "2048"
    end
    app.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision.yml"
    #ansible.verbose = "vvvv"
  end

end
