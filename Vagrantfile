
rstudio_node_name = "rstudio-server"

Vagrant.configure("2") do |config|

  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
  config.ssh.forward_x11 = true

  config.vm.define :rstudio do |rstudio|
    rstudio.vm.box = "precise64"
    rstudio.vm.provider :virtualbox do |v|
      v.name = rstudio_node_name
      v.customize ["modifyvm", :id, "--memory", "4096"]
    end
    rstudio.vm.network :private_network, ip: "10.211.55.110"
    rstudio.vm.hostname = rstudio_node_name
    rstudio.vm.provision :shell, :path => "rstudio_node.sh"
  end

end

