Vagrant.configure("2") do |config|
  
  config.vm.define "local-engineering" do |wilbuild|
    wilbuild.vm.box = "ubuntu/bionic64"
    wilbuild.vm.provider :virtualbox do |v, override|
      v.memory = 1024
      v.cpus = 2
    end
    
    wilbuild.vm.provision "file", source: ".ansible.cfg", destination: "/home/vagrant/.ansible.cfg"

    wilbuild.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end

    wilbuild.vm.provision "shell" do |shell|
      #shell.path = "pkg-install.sh"
      shell.inline = "apt install cowsay"
    end
  end

end