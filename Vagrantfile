# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  
  ### Load Balancer Nginx VM

  config.vm.define "web01" do |web01|
    web01.vm.box = "ubuntu/bionic64"
    web01.vm.hostname = "web01"
    web01.vm.network "private_network", ip: "192.168.44.11"
    web01.vm.boot_timeout = 600
  end

  ### TomCat Web Server VM
  config.vm.define "app01" do |app01|
    app01.vm.box = "geerlingguy/centos7"
    app01.vm.hostname = "app01"
    app01.vm.network "private_network", ip: "192.168.44.12"
    app01.vm.boot_timeout = 600
	app01.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
	 end
  end
   
  ### RabbitMQ Message Broker VM
  config.vm.define "rmq01" do |rmq01|
    rmq01.vm.box = "geerlingguy/centos7"
	  rmq01.vm.hostname = "rmq01"
    rmq01.vm.network "private_network", ip: "192.168.44.16"
    rmq01.vm.boot_timeout = 600
  end
  
  ### Memcache VM   
  config.vm.define "mc01" do |mc01|
    mc01.vm.box = "geerlingguy/centos7"
	  mc01.vm.hostname = "mc01"
    mc01.vm.network "private_network", ip: "192.168.44.14"
    mc01.vm.boot_timeout = 600
  end
  
  ### DB VM  
  config.vm.define "db01" do |db01|
    db01.vm.box = "geerlingguy/centos7"
	  db01.vm.hostname = "db01"
    db01.vm.network "private_network", ip: "192.168.44.15"
    db01.vm.boot_timeout = 600
  end
end