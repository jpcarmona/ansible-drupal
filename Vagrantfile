Vagrant.configure("2") do |config|

  config.vm.box = "debian/stretch64"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 1
  end
  
    config.vm.define "nodo1" do |nodo1|

      config.vm.provider "virtualbox" do |vb|
        vb.name = "nodo1"
      end

      nodo1.vm.hostname = "db-dns"
      nodo1.vm.network "private_network",
        ip: "192.168.56.101",
        name: "vboxnet0",
        adapter: 2
      nodo1.vm.network "forwarded_port",
        guest: 5432,
        host: 2345,
        adapter: 1
    end
  
    config.vm.define "nodo2" do |nodo2|

      config.vm.provider "virtualbox" do |vb|
        vb.name = "nodo2"
      end

      nodo2.vm.hostname = "web-drupal"
      nodo2.vm.network "private_network",
        ip: "192.168.56.102",
        name: "vboxnet0",
        adapter: 2
    end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "ansible/playbook.yml"
    ansible.become = true
    ansible.config_file = "ansible/ansible.cfg"
  end

end
