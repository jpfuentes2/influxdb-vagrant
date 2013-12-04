#!/usr/bin/env ruby

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.network "forwarded_port", :guest => 8083, :host => 8083
  config.vm.network "forwarded_port", :guest => 8086, :host => 8086

  config.ssh.forward_agent = true

  cmd = "apt-get update -qq;
          wget -quiet http://s3.amazonaws.com/influxdb/influxdb_latest_amd64.deb;
          dpkg -i influxdb_latest_amd64.deb;"
  config.vm.provision :shell, :inline => cmd
end
