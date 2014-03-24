# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
apt-get update -y
apt-get install -y flex bison build-essential csh openjdk-6-jdk libxaw7-dev
mkdir /usr/class
chown vagrant /usr/class
cd /usr/class
wget http://spark-university.s3.amazonaws.com/stanford-compilers/vm/student-dist.tar.gz
tar -xf student-dist.tar.gz
ln -s /usr/class/cs143/cool ~vagrant/cool
echo 'export PATH=/usr/class/cs143/cool/bin:$PATH' >> ~vagrant/.profile
SCRIPT

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.synced_folder "cool", "/usr/class/cs143/cool"
  config.vm.provision "shell", inline: $script
end
