Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
 
  config.vm.define "web1" do |web1|
    web1.vm.box = "geerlingguy/ubuntu2004"
    web1.vm.hostname = "web1"
    web1.vm.network "private_network", ip: "192.168.60.11"
    web1.vm.provision :docker
    web1.vm.provision :docker_compose
  end

  config.vm.provider "virtualbox" do |vb|
    vb.name = "web1"
    vb.memory = "2048"
    vb.cpus = "1"
  end  
end


