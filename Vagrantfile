# -*- mode: ruby -*-
# vi: set ft=ruby :

$provisionScript = <<-SCRIPT
sed -i 's#PasswordAuthentication no#PasswordAuthentication yes#g' /etc/ssh/sshd_config
systemctl restart sshd
SCRIPT

Vagrant.configure("2") do |config|

 config.vm.provision "shell",
 inline: $provisionScript

 config.vm.define "centos1" do |centos1|
   centos1.vm.box = "centos/7"
   centos1.vm.network "private_network", ip: "192.168.33.10"
   centos1.vm.network "private_network", ip: "192.168.44.10", auto_config: false
   centos1.vm.hostname = "centos1"
 config.vm.provider "hyperv" do |centos1|
   centos1.memory =  "1024"
   centos1.cpus = "1"
   end

 end

 config.vm.define "centos2" do |centos2|
   centos2.vm.box = "centos/7"
   centos2.vm.network "private_network", ip: "192.168.33.11"
   centos2.vm.network "private_network", ip: "192.168.44.11", auto_config: false
   centos2.vm.hostname = "centos2"
 end
 config.vm.provider "hyperv" do |centos2|
   centos2.memory =  "1024"
   centos2.cpus = "1"
   end

 config.vm.define "centos3" do |centos3|
   centos3.vm.box = "centos/7"
   centos3.vm.network "private_network", ip: "192.168.33.12"
   centos3.vm.network "private_network", ip: "192.168.44.12", auto_config: false
   centos3.vm.hostname = "centos3"
 end
 config.vm.provider "hyperv" do |centos3|
   centos3.memory =  "1024"
   centos3.cpus = "1"
   end

=begin
 config.vm.define "ubuntu1" do |ubuntu1|
   ubuntu1.vm.box = "generic/ubuntu1804"
   ubuntu1.vm.hostname = "ubuntu1"
 end
 config.vm.provider "hyperv" do |ubuntu1|
   centos1.memory =  "1024"
   centos1.cpus = "1"
   end
=end
end
