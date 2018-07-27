VAGRANTFILE_API_VERSION = "2"
 
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/trusty64"
 
    config.vm.provider "virtualbox" do |vb|
        vb.cpus = 2
    end
 
    config.vm.network "private_network", ip: "192.168.56.10"
    config.vm.network "forwarded_port", guest: 80, host: 8080

    #https://www.vagrantup.com/docs/provisioning/salt.html
    ## Use all the defaults:
    config.vm.provision :salt do |salt|
      salt.masterless = true
      salt.minion_config = "salt/minion"
      salt.run_highstate = true
    end
end
