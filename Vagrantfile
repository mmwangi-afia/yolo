Vagrant.configure("2") do |config|
  # Use Ubuntu 20.04 LTS
  config.vm.box = "ubuntu/focal64"

  # Configure VM resources
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end

  # Keep both networking options
  config.vm.network "private_network", ip: "192.168.56.10"
  config.vm.network "forwarded_port", guest: 22, host: 2222, host_ip: "0.0.0.0"
  config.vm.network "forwarded_port", guest: 3000, host: 3000, host_ip: "0.0.0.0"
  config.vm.network "forwarded_port", guest: 5000, host: 5000, host_ip: "0.0.0.0"
  config.vm.network "forwarded_port", guest: 27017, host: 27017, host_ip: "0.0.0.0"

  # Ensure vagrant user has passwordless sudo
  config.vm.provision "shell", inline: <<-SHELL
    echo "vagrant ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/vagrant
    chmod 0440 /etc/sudoers.d/vagrant
  SHELL
end
