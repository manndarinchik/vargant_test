# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|=
  config.vm.box = "ubuntu/jammy64" # Ubuntu 22.04 LTS
  config.vm.box_check_update = false

  (1..2).each do |i|
    config.vm.define "ubuntu#{i}" do |node|
      node.vm.hostname = "ubuntu#{i}"
      node.vm.synced_folder "./data", "/vagrant_data", type: "rsync",
        rsync__exclude: ".git/", 
        rsync__auto: true                       
      node.vm.provision "file", source: "./test.txt", destination: "/home/vagrant/test.txt"
    end
  end
end