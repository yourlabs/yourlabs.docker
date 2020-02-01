# -*- mode: ruby -*-
# vi: set ft=ruby :
require 'fileutils'

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.ssh.forward_agent = true

  config.vm.box = "bento/ubuntu-18.04"

  FileUtils.mkdir_p ".vagrant/cache/apt"
  config.vm.synced_folder ".vagrant/cache/apt", "/var/cache/apt"

  FileUtils.mkdir_p ".vagrant/cache/pip"
  config.vm.synced_folder ".vagrant/cache/pip", "/root/.cache/pip"

  if ENV['VAGRANT_IP']
    config.vm.network "private_network", ip: ENV['VAGRANT_IP']
  else
    config.vm.network "private_network", type: "dhcp"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.gui = ENV['VAGRANT_GUI']
    vb.memory = "1024"
    vb.cpus = 2
  end
end

