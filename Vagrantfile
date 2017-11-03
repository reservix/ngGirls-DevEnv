Vagrant.configure("2") do |config|

  # create virtual machine
  config.vm.provider "virtualbox" do |virtualbox|
    virtualbox.memory = 8192
    virtualbox.cpus = 4
    virtualbox.customize ["modifyvm", :id, "--hwvirtex", "on"]
  end

  # configure virtual machine
  config.vm.define "ngGirls" do |ngGirls|
    ngGirls.vm.box = "ubuntu/xenial64"
    ngGirls.vm.hostname = 'ngGirls'
    ngGirls.vm.network :private_network, ip: "192.168.33.25"
  end

  # install python
  config.vm.provision "shell",
    inline: "export DEBIAN_FRONTEND=noninteractive; apt -y install python"

  # run ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "inventory"
    ansible.sudo = true
  end
end
