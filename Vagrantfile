Vagrant.configure("2") do |config|

  config.vm.define "nodo1" do |nodo1|

    config.vm.provider "virtualbox" do |vb|
      vb.name = "nodo1"
      vb.cpus = 1
    end

    nodo1.vm.box = "debian/stretch64"
    nodo1.vm.hostname = "nodo1"
    nodo1.vm.network "private_network",
      ip: "192.168.56.101",
      name: "vboxnet0",
      adapter: 2
  end

  config.vm.define "nodo2" do |nodo2|

    config.vm.provider "virtualbox" do |vb|
      vb.name = "nodo2"
      vb.cpus = 1

    end

    nodo2.vm.box = "debian/stretch64"
    nodo2.vm.hostname = "nodo2"
    nodo2.vm.network "private_network",
      ip: "192.168.56.102",
      name: "vboxnet0",
      adapter: 2
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "ansible.yml"
    ansible.inventory_path = "./ansible_hosts"
  end

end
