# -*- mode: ruby -*-
# vi: set ft=ruby :

# Change next variables if necessary:

CPU_CORES_COUNT = "4"
MEMORY_COUNT = "4096"
IP_ADDRESS = "192.168.56.100"

Vagrant.configure(2) do |config|
    config.ssh.insert_key = false
    config.vm.box = "voidead/win-xp-sp1"
    config.vm.provider "virtualbox" do |v|
    config.vm.network "private_network", ip: IP_ADDRESS
    config.vm.synced_folder "shared", "C:\\", type: "virtualbox"
    end

    config.vm.define 'windows' do |windows|
        windows.vm.network :private_network, ip: IP_ADDRESS
        windows.vm.synced_folder "shared", "C:\\"
        windows.vm.hostname = "windows-xp"
        windows.vm.provider "virtualbox" do |v|
            v.customize ["modifyvm", :id, "--vram", "32"]
            v.name = "windows-xp"
            v.memory = MEMORY_COUNT
            v.cpus = CPU_CORES_COUNT
            v.gui = true
        end
    end

end
