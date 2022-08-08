Vagrant.configure("2") do |config|

#--------------------------------CentOS-----------------------------------------

    config.vm.define "centos" do |centos|
        centos.vm.hostname = "centos"
        centos.vm.box = "generic/centos8s"
        centos.vm.network "public_network", bridge: "br0", ip: "192.168.0.151"

        centos.vm.provider "virtualbox" do |vb|
            vb.name = "centos"
            vb.cpus = 2
            vb.memory = "4096"
        end

     centos.vm.provision "shell", inline: <<-SHELL
        sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
        systemctl restart sshd.service
        sudo echo "root:toor" | chpasswd
    SHELL
   end
##############################################################
end
