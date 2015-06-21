# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|

  # Use ubuntu base
  config.vm.box = "ubuntu/trusty64"

  # Forward YARN UI ports
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 8042, host: 8042

  # Configure VM provider
  config.vm.provider "virtualbox" do |vm|
    vm.memory = 8_192 # Give VM enough memory (in MB) to run spark
  end

  # Run docker images
  config.vm.provision "docker" do |d|
    d.run "sequenceiq/spark"
  end
end
