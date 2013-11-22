# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "precise64"
    config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    config.vm.network :forwarded_port, guest: 8080, host: 1223

    config.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--memory", 2048]
    end

    config.vm.provision :ansible do |ansible|
      ansible.playbook = "reviewboard.yml"
      ansible.sudo = true
      # debug is on
      ansible.verbose = "vvvv"
    end


end
