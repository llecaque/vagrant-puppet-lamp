VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

        config.vm.box = "taobox"
        config.vm.box_url = "http://files.vagrantup.com/lucid32.box"
	config.vm.network :forwarded_port, guest: 80, host: 8000

        config.vm.host_name = "tao.box"

        config.vm.provider :virtualbox do |vb|
		vb.gui = false
		vb.customize ["modifyvm", :id, "--name", "Ubuntu 12.04"]
		#vb.customize ["modifyvm", :id, "--memory", "512"]
	end


	config.vm.provision :puppet do |puppet|
    		puppet.manifests_path = "puppet/manifests"
		puppet.module_path    = "puppet/modules"
		puppet.manifest_file  = "base.pp"
	end

        
        #inv_config.vm.provision :shell, :path => "puppet/scripts/enable_remote_mysql_access.sh"
    end

