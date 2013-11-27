# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"

  # Forward a port from the guest to the host, which allows for outside
  # computers to access the VM, whereas host only networking does not.
  # config.vm.forward_port 80, 8080
  config.vm.forward_port 27017, 27017
  config.vm.forward_port 8080, 8125

  # Enable provisioning with chef solo, specifying a cookbooks path (relative
  # to this Vagrantfile), and adding some recipes and/or roles.
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = [ "cookbooks" ]
    chef.add_recipe "mongodb-10gen::single"
    chef.add_recipe "java"
    chef.add_recipe "setup-mongo::default"
    chef.add_recipe "tomcat"
    chef.add_recipe "setup-tomcat"

  #   # You may also specify custom JSON attributes:
  #   chef.json = { :mysql_password => "foo" }
  end

end
