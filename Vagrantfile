# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|

  # Use ubuntu base
  config.vm.box = "ubuntu/trusty64"

  # Forward YARN resource manager UI port
  config.vm.network "forwarded_port", guest: 8088, host: 8088

  # Forward YARN node manager UI port
  config.vm.network "forwarded_port", guest: 8042, host: 8042

  # Forward YARN resource manager port
  config.vm.network "forwarded_port", guest: 8032, host: 8032

  # Configure VM provider
  config.vm.provider "virtualbox" do |vm|
    vm.memory = 8_192 # Give VM enough memory (in MB) to run spark
  end

  # Run docker images
  config.vm.provision "docker" do |d|
    d.run "sequenceiq/hadoop-docker:2.7.0"
    d.run "sequenceiq/spark"
  end
end
