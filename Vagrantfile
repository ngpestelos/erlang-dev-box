# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ringtail64"
  config.vm.synced_folder ".", "/vagrant"
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["chef/cookbooks"]
    chef.add_recipe "recipe[locale]"
    chef.add_recipe "recipe[apt]"
    chef.add_recipe "recipe[build-essential]"
    chef.add_recipe "recipe[vim]"
    chef.add_recipe "recipe[openssl]"
    chef.add_recipe "recipe[yum]"
    chef.add_recipe "recipe[erlang]"
    chef.json = {
      :erlang => {
        :install_method => 'source',
        :source => {
          :version => 'R16B01',
          :url => 'http://www.erlang.org/download/otp_src_R16B01.tar.gz'
        }
      }
    }
  end
end
