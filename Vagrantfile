Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
 
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end
 
  config.vm.network :forwarded_port, guest: 80, host: 8888
    config.vm.provision :chef_solo do |chef|
        chef.add_recipe "apache2"
        chef.json = { :apache => { :default_site_enabled => true } }
    end

  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
