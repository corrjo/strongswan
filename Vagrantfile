# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 :

Vagrant.configure("2") do |config|
  config.vm.box = "dummy"

  config.vm.provider :aws do |aws, override|
    aws.keypair_name = "KEYPAIR"

    aws.ami = "ami-1ee65166"
    aws.region = "us-west-2"
    aws.associate_public_ip = true
    aws.security_groups = ["SOME_SG_YOU_CREATED"]
    aws.instance_type = "c5.large"
    aws.subnet_id = "subnet-ed8284b4"

    override.ssh.username = "ubuntu"
    override.ssh.private_key_path = "~/.ssh/KEYPAIR"
    config.vm.provision "shell",
      inline: "sudo apt -y install python"
    #Provisionng Config for ansible.
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "tests/test.yml"
      ansible.become = true
    end
  end
end

