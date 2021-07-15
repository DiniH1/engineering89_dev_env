# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|


 config.vm.define "app" do |app|
    app.vm.box = "ubuntu/xenial64"
    app.vm.network "private_network", ip: "192.168.10.100"
    app.hostsupdater.aliases = ["development.local"]
    app.vm.synced_folder ".", "/home/vagrant/environment"
    app.vm.provision "shell", path: "environment/provision.sh"
 end

 config.vm.define "db" do |db|
  db.vm.box = "ubuntu/xenial64"
  db.vm.network "private_network", ip: "192.168.10.150"
  db.hostsupdater.aliases = ["database.local"]
#db.vm.synced_folder "environment/db", "/home/ubuntu/environment"
#db.vm.provision "shell", path: "environment/db/provision.sh", privileged: false
 end
end