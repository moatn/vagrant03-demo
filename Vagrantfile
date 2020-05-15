# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|

    # Ssh settings
    config.ssh.insert_key = false

    # Default settings
    config.vm.box = "ubuntu/bionic64"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 512
        vb.cpus = 1
    end

    config.vm.define :lb01 do |machine|
        machine.vm.host_name = "lb01.local"
        machine.vm.network "private_network", ip: "192.168.50.10"

        machine.vm.provision "ansible_local", preserve_order: true do |ansible|
            ansible.playbook = "provision/default.yml"
            ansible.install_mode = :pip
            ansible.pip_install_cmd = "sudo apt install python3 python3-pip -y; sudo ln -s /usr/bin/pip3 /usr/bin/pip"
            ansible.compatibility_mode = '2.0'
        end
    end

    config.vm.define :web01 do |machine|
        machine.vm.host_name = "web01.local"
        machine.vm.network "private_network", ip: "192.168.50.12"

        machine.vm.provision "ansible_local", preserve_order: true do |ansible|
            ansible.playbook = "provision/default_web01.yml"
            ansible.install_mode = :pip
            ansible.pip_install_cmd = "sudo apt install python3 python3-pip -y; sudo ln -s /usr/bin/pip3 /usr/bin/pip"
            ansible.compatibility_mode = '2.0'
        end
    end

    config.vm.define :web02 do |machine|
        machine.vm.host_name = "web02.local"
        machine.vm.network "private_network", ip: "192.168.50.13"

        machine.vm.provision "ansible_local", preserve_order: true do |ansible|
            ansible.playbook = "provision/default_web02.yml"
            ansible.install_mode = :pip
            ansible.pip_install_cmd = "sudo apt install python3 python3-pip -y; sudo ln -s /usr/bin/pip3 /usr/bin/pip"
            ansible.compatibility_mode = '2.0'
        end
    end
end

