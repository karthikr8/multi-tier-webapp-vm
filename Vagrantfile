# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true

  ### DB VM  
  config.vm.define "db01" do |db01|
    db01.vm.box = "eurolinux-vagrant/centos-stream-9"
	  db01.vm.hostname = "db01"
    db01.vm.network "private_network", ip: "192.168.44.15"
    db01.vm.boot_timeout = 600
    db01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
	  end
    db01.vm.provision "shell", path: "provision_db.sh"
  end  

  ### Memcache VM   
  config.vm.define "mc01" do |mc01|
    mc01.vm.box = "eurolinux-vagrant/centos-stream-9"
	  mc01.vm.hostname = "mc01"
    mc01.vm.network "private_network", ip: "192.168.44.14"
    mc01.vm.boot_timeout = 600
    mc01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
	  end
    mc01.vm.provision "shell", path: "provision_mc.sh"
  end

  ### RabbitMQ Message Broker VM
  config.vm.define "rmq01" do |rmq01|
    rmq01.vm.box = "eurolinux-vagrant/centos-stream-9"
	  rmq01.vm.hostname = "rmq01"
    rmq01.vm.network "private_network", ip: "192.168.44.16"
    rmq01.vm.boot_timeout = 600
    rmq01.vm.provider "virtualbox" do |vb|
      vb.memory = "600"
	  end
    rmq01.vm.provision "shell", path: "provision_rmq.sh"
  end  
  
  ### TomCat Web Server VM
  config.vm.define "app01" do |app01|
    app01.vm.box = "eurolinux-vagrant/centos-stream-9"
    app01.vm.hostname = "app01"
    app01.vm.network "private_network", ip: "192.168.44.12"
    app01.vm.boot_timeout = 600
	  app01.vm.provider "virtualbox" do |vb|
      vb.memory = "800"
	  end
    app01.vm.provision "shell", path: "provision_app.sh"
  end

  ### Load Balancer Nginx VM

  config.vm.define "web01" do |web01|
    web01.vm.box = "ubuntu/jammy64"
    web01.vm.hostname = "web01"
    web01.vm.network "private_network", ip: "192.168.44.11"
    web01.vm.boot_timeout = 600
    web01.vm.provider "virtualbox" do |vb|
      vb.memory = "800"
	  end
    web01.vm.provision "shell", path: "provision_web.sh"
  end

end