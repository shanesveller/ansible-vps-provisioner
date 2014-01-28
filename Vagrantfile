# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :nginx do |nginx|
    nginx.vm.box = "raring64-vanilla"

    nginx.vm.box_url = "http://shanesveller-files.s3.amazonaws.com/raring64-vanilla.box"

    nginx.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--memory", 2048]
    end

    # Boot with a GUI so you can see the screen. (Default is headless)
    # config.vm.boot_mode = :gui

    # config.vm.network :hostonly, "192.168.33.10"

    nginx.vm.network :forwarded_port, guest: 80, host: 8080

    nginx.vm.network :private_network, ip: "192.168.111.2"

    nginx.vm.provision :ansible do |ansible|
      ansible.playbook = "vps.yml"
      ansible.inventory_path = "staging"
      ansible.verbose = true
      ansible.sudo = true
    end
  end
end
