Vagrant.configure("2") do |config|
  # Use Ubuntu 20.04 LTS
  config.vm.box = "ubuntu/focal64"

  # Configure VM resources
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
  end

  # Forward SSH so Ansible can connect
  config.vm.network "private_network", type: "dhcp"

  # Disable synced folder for simplicity (optional)
  # config.vm.synced_folder ".", "/vagrant", disabled: true
end
