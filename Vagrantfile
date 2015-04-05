# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "mitchellh/boot2docker"
  config.vm.network "private_network", ip: "192.168.50.4"
  config.vm.define "docker-host-vm" do |t|
  end

  config.vm.provider "virtualbox" do |v|
    # On VirtualBox, we don't have guest additions or a functional vboxsf
    # in TinyCore Linux, so tell Vagrant that so it can be smarter.
    v.check_guest_additions = false
    v.functional_vboxsf     = false
  end

  # b2d doesn't support NFS
  config.nfs.functional = false

  # b2d doesn't persist filesystem between reboots
  if config.ssh.respond_to?(:insert_key)
    config.ssh.insert_key = false
  end
end
