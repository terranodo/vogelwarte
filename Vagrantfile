# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/20160208/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.ssh.username = 'vagrant'

  config.vm.define :production do |production|
  	production.vm.network :public_network, :bridge => 'eth0', :auto_config => false
    config.vm.network "forwarded_port", guest: 8000, host: 8000
    production.vm.provider :virtualbox do |vb|
        vb.customize [ "modifyvm", :id, "--name", "Vogelwarte-Production","--memory", 4096 ]
  	end
    config.vm.provision "ansible" do |ansible|
	ansible.host_key_checking = false
	ansible_inventory_path = "inventory.ini"
        ansible.playbook = "playbook.yml"
    end
    config.vm.network :private_network, ip: "192.168.56.151"
  end

end
