Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.network :forwarded_port, guest: 8080, host: 4567
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 1
  end	
end
