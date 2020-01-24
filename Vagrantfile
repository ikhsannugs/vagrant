Vagrant.configure("2") do |config|
 config.vm.provision "shell", inline: "git clone https://github.com/ikhsannugs/project1-cilsy.git"
  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
  end
   config.vm.define "master" do |master|
    master.vm.provision "shell", inline: "chmod 777 /home/vagrant/project1-cilsy/loadbal.sh"
    master.vm.provision "shell", inline: "/bin/sh /home/vagrant/project1-cilsy/loadbal.sh"
    master.vm.network "public_network", bridge: "wlp3s0",
       use_dhcp_assigned_default_route: true
    master.vm.box = "ubuntu/bionic64"
    master.vm.network "private_network",ip: "100.100.100.1"
   end

      config.vm.define "firstlb" do |firstlb|
         firstlb.vm.provision "shell", inline: "chmod 777 /home/vagrant/project1-cilsy/backend.sh"
         firstlb.vm.provision "shell", inline: "/bin/sh /home/vagrant/project1-cilsy/backend.sh"
         firstlb.vm.box = "ubuntu/bionic64"
         firstlb.vm.network "private_network",ip: "100.100.100.3"
      end

      config.vm.define "seclb" do |seclb|
         seclb.vm.provision "shell", inline: "chmod 777 /home/vagrant/project1-cilsy/backend.sh"
         seclb.vm.provision "shell", inline: "/bin/sh /home/vagrant/project1-cilsy/backend.sh"
         seclb.vm.box = "ubuntu/bionic64"
         seclb.vm.network "private_network",ip: "100.100.100.3"
      end

end
