Vagrant.configure("2") do |config|
  config.vm.box = 'centos/7'
  config.vm.network "public_network", bridge: "Wan"

  config.vm.define "vm01" do |vm01|
    vm01.vm.hostname = "vm01.infra.vm"
    vm01.vm.provider "hyperv" do |v|
      v.memory = 1024
      v.cpus = 1
    end
  end
  
  config.vm.define "vm02" do |vm02|
    vm02.vm.hostname = "vm02.infra.vm"
    vm02.vm.provider "hyperv" do |v|
      v.memory = 1024
      v.cpus = 1   
    end
  end
  
end