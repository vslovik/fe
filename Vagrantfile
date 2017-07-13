Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"

    config.vm.provision "shell", inline: <<-SHELL
        sudo apt-get -y install python-minimal
    SHELL

    config.vm.provision :ansible do |ansible|
        #ansible.verbose = "vvv"
        ansible.playbook = "playbook.yml"
        #ansible.install  = true
        #ansible.version  = "latest"
    end
end
