Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 1
  end
  
  config.vm.define "nodo1" do |nodo1|

    config.vm.provider "virtualbox" do |vb|
      vb.name = "drupal"
    end

    nodo1.vm.box = "centos/6"

    nodo1.vm.hostname = "drupal"
    nodo1.vm.network "public_network",
      bridge: "enp3s0",
      adapter: 2

    nodo1.vm.provision "ansible" do |ansible|
      ansible.verbose = "v"
      ansible.playbook = "playbook_centos6_update.yml"
      ansible.become = true
      #ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
    end

  end

end
