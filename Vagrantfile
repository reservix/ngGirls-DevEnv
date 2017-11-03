Vagrant.configure("2") do |config|

  #using generated key not working
  config.ssh.insert_key = false
  # specs for all vms
  config.vm.provider "virtualbox" do |v|
    v.memory = 8192
    v.cpus = 4
    v.customize ["modifyvm", :id, "--hwvirtex", "on"]
  end

  config.vm.define "ngGirls" do |ngGirls|
    ngGirls.vm.box = "geerlingguy/ubuntu1604"
    ngGirls.vm.hostname = 'ngGirls'
    ngGirls.vm.network :private_network, ip: "192.168.33.25"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "inventory"
    ansible.sudo = true
  end
end
