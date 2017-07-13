Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"

    config.vm.network :private_network, ip: "192.168.10.11", netmask: "255.255.255.0"

    config.hostmanager.aliases = %w(fe)
    config.hostmanager.enabled = true
    config.hostmanager.manage_host = true
    config.hostmanager.ignore_private_ip = false
    config.hostmanager.include_offline = true

    config.vm.synced_folder "../fe_app", "/opt/fe_app", nfs: true

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
