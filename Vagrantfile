# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "trusty-amd64-current"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  if Vagrant.has_plugin?("vagrant-hostsupdater")
    config.hostsupdater.remove_on_suspend = true
  end

  config.vm.hostname = "kurento.test"
  config.vm.network :private_network, ip: "192.168.10.10"

  config.vm.provision :shell, :inline => <<-EOS
    add-apt-repository ppa:kurento/kurento
    apt-get update -y
    apt-get install -y kurento-media-server
    service kurento-media-server start
  EOS
end
