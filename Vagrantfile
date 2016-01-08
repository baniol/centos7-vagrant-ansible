Vagrant.configure("2") do |config|
    config.vm.box = "ancient/Centos7.Ansible"
    config.vm.network :private_network, ip: "192.168.33.13"

    config.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end

    config.vm.synced_folder "./Projects/", "/home/vagrant/Projects"
    #config.vm.synced_folder "./provision/", "/home/vagrant/provision"
    #config.vm.synced_folder "./Projects", "/home/vagrant/Projects", :nfs => true, :mount_options => ['nolock,vers=3,udp,noatime,fsc,actimeo=1']

    config.ssh.username = 'vagrant'
    config.ssh.password = 'vagrant'
    config.ssh.insert_key = 'true'

    config.vbguest.auto_update = false

    #config.vm.provision :shell, :inline => "ansible-playbook provision/playbook.yml"

    config.vm.provision :ansible do |ansible|
      ansible.playbook = "provision/playbook.yml"
    end
end
