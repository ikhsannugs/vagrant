Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "apt-get update && apt-get install -y  docker.io "

  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/xenial64"
    master.vm.network "private_network",ip: "192.168.100.3"
      master.vm.provider "virtualbox" do |v|
        v.memory = 2024
        v.cpus = 2
     end
  end

  config.vm.define "node1" do |node1|
    node1.vm.box = "ubuntu/xenial64"
    node1.vm.network "private_network",ip: "192.168.100.2"
  end

 config.vm.define "node2" do |node2|
    node2.vm.box = "ubuntu/xenial64"
    node2.vm.network "private_network",ip: "192.168.100.2"
  end
 config.vm.define "node2" do |node2|
    node2.vm.box = "ubuntu/xenial64"
    node2.vm.network "private_network",ip: "192.168.100.4"
  end

 config.vm.define "jenkins" do |jenkins|
    jenkins.vm.box = "ubuntu/xenial64"
    jenkins.vm.network "private_network",ip: "192.168.100.5"
  end
 config.vm.define "gitlab" do |gitlab|
    gitlab.vm.box = "ubuntu/xenial64"
    gitlab.vm.network "private_network",ip: "192.168.100.6"
  end

  config.vm.define "lb" do |lb|
    lb.vm.box = "ubuntu/xenial64"
    lb.vm.network "private_network",ip: "192.168.100.7"
  end

end
