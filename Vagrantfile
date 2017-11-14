# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento/centos-6.8"
  config.vm.provider "parallels" do |v, override|
    override.vm.box = "parallels/centos-6.8"
  end

  config.vm.hostname = "webpagetest.local"

  config.vm.network :forwarded_port, guest: 80, host: 8086
  config.vm.network :private_network, ip: "192.168.33.33"

  config.vm.provision "ansible" do |ansible|
    ansible.inventory_path = "hosts"
    ansible.limit = "all"
    ansible.playbook = "webpagetest-private.yml"
    ansible.verbose = "vv"
  end

end
