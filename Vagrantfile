# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "bento/centos-6.7"

  config.vm.hostname = "webpagetest.local"

  config.vm.network :forwarded_port, guest: 80, host: 8086
  config.vm.network :private_network, ip: "192.168.33.33"

  config.vm.provision "shell", privileged: true, inline: "rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm"
  config.vm.provision "shell", privileged: true, inline: "yum install -y ansible"
  config.vm.provision "shell", privileged: true, inline: "ansible-playbook -vv -i /vagrant/hosts /vagrant/webpagetest-private.yml"

end
