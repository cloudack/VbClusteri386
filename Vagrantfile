# -*- mode: ruby -*-
# vi: set ft=ruby :
#Vagrant::Config.run do |config|
Vagrant.configure("2") do |config|
 
 config.vm.define :node1 do |agent|
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", 1024]
     end
     agent.vm.hostname = "cloudack-mnds1-1.hdp.net"
     agent.vm.box = "centos_i386"
     agent.vm.box_url = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-i386-v20131103.box"
     agent.vm.network :private_network, ip: "192.168.33.11"
     agent.vm.network :forwarded_port, host: 7000, guest: 50070
     agent.vm.network :forwarded_port, host: 7001, guest: 8088
     agent.vm.network :forwarded_port, host: 7002, guest: 60010
     agent.vm.synced_folder "vm", "/etc/share/vm"
     agent.vm.provision :shell, :path => "kickstart.sh"


 end

 config.vm.define :node2 do |agent|
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", 1024]
     end
     agent.vm.hostname = "cloudack-dnds1-1.hdp.net"
     agent.vm.box = "centos_i386"
     agent.vm.box_url = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-i386-v20131103.box"
     agent.vm.network :private_network, ip: "192.168.33.12"
     agent.vm.network :forwarded_port, host: 9000, guest: 50070
     agent.vm.network :forwarded_port, host: 9001, guest: 8088
     agent.vm.network :forwarded_port, host: 9002, guest: 60010
     agent.vm.synced_folder "vm", "/etc/share/vm"
     agent.vm.provision :shell, :path => "dkickstart.sh"
 end

 config.vm.define :node3 do |agent|
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", 1024]
     end
     agent.vm.hostname = "cloudack-dnds1-2.hdp.net"
     agent.vm.box = "centos_i386"
     agent.vm.box_url = "http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-i386-v20131103.box"
     agent.vm.network :private_network, ip: "192.168.33.13"
     agent.vm.synced_folder "vm", "/etc/share/vm"
     agent.vm.provision :shell, :path => "dkickstart.sh"
 end

end

