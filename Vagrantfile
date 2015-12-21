Vagrant.configure("2") do |config|
    config.vm.box = "centos7.1"
    config.vm.box_url = "https://github.com/CommanderK5/packer-centos-template/releases/download/0.7.1/vagrant-centos-7.1.box"
    #config.vm.network :forwarded_port, guest: 3000, host: 3000
    config.vm.network :private_network, ip: "192.168.33.10"
    #config.vm.network "public_network"

    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end

    #config.vm.synced_folder "./Projects/", "/root/Projects"

    config.ssh.username = 'root'
    config.ssh.password = 'vagrant'
    #config.ssh.private_key_path = './roles/user/files/authorized_keys'
    config.ssh.insert_key = 'true'

   config.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
   end
end
