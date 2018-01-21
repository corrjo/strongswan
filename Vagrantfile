# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 :


Vagrant.configure("2") do |config|

  config.ssh.insert_key = false
  config.landrush.tld = "dev"
  rolename = File.basename(Dir.getwd)
  hostname = "#{rolename}.#{config.landrush.tld}".sub('_','-')

  config.vm.define "vagrantbox" do |vagrantbox|
    vagrantbox.vm.box = "bento/ubuntu-16.10"
    config.vm.network "public_network"

    if Vagrant.has_plugin?("vagrant-cachier")
      vagrantbox.cache.scope = :box
    end

    if Vagrant.has_plugin?("landrush")
        config.landrush.enabled = true
        vagrantbox.vm.hostname = "#{hostname}"
    else
        vagrantbox.vm.hostname = "#{config.rolename}.vagrant.box"
    end

    #Provisionng Config for ansible.
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "tests/test.yml"
      ansible.sudo = true
    end
  end
end
