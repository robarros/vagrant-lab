Vagrant.configure("2") do |config|
  config.vm.box = 'centos/7'
  config.vm.network "public_network", bridge: "Default Switch"
  config.vm.synced_folder ".", "/vagrant"
  config.ssh.insert_key = false
  config.ssh.private_key_path = ["C:/Users/Ronaldo/.ssh/id_rsa", "~/.vagrant.d/insecure_private_key"]
  config.vm.provision "file", source: "C:/Users/Ronaldo/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"

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
    vm02.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end
  
end

